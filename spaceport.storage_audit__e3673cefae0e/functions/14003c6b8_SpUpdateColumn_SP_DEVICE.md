# SpUpdateColumn(SP_DEVICE *)

- ea: `0x14003c6b8`
- end: `0x14003ca10`
- name: `?SpUpdateColumn@@YAJPEAVSP_DEVICE@@@Z`
- size: `856`
- prototype: `__int64 __fastcall(struct SP_DEVICE *this)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14002b360`
- `0x14002b608`
- `0x14003ca20`

## callees

- `0x14000200c`
- `0x1400034dc`
- `0x14000b3e0`
- `0x140011970`
- `0x14001d3f0`
- `0x1400216f0`
- `0x140021a90`
- `0x14003c604`
- `0x14003c6b8`
- `0x1400439b4`
- `0x140067fc0`
- `0x1400684c0`
- `0x1400b5720`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c9e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c9e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c9d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c9d6`

## pseudocode

```c
__int64 __fastcall SpUpdateColumn(SP_SPACE **this)
{
  SP_SPACE *v2; // rbx
  int updated; // esi
  int v4; // edi
  struct SDB_RECORD *SpaceById; // rax
  int v6; // eax
  int v7; // r8d
  int v8; // r9d
  int v10; // [rsp+A0h] [rbp-80h] BYREF
  int v11; // [rsp+A4h] [rbp-7Ch] BYREF
  int v12; // [rsp+A8h] [rbp-78h] BYREF
  int v13; // [rsp+ACh] [rbp-74h] BYREF
  int v14; // [rsp+B0h] [rbp-70h] BYREF
  int v15; // [rsp+B4h] [rbp-6Ch] BYREF
  int v16; // [rsp+B8h] [rbp-68h] BYREF
  char *v17; // [rsp+C0h] [rbp-60h] BYREF
  char *v18; // [rsp+C8h] [rbp-58h] BYREF
  _DWORD *v19; // [rsp+D0h] [rbp-50h] BYREF
  int v20; // [rsp+D8h] [rbp-48h]
  _DWORD *v21; // [rsp+E0h] [rbp-40h] BYREF
  int v22; // [rsp+E8h] [rbp-38h]
  _DWORD *v23; // [rsp+F0h] [rbp-30h] BYREF
  int v24; // [rsp+F8h] [rbp-28h]
  _DWORD *v25; // [rsp+100h] [rbp-20h] BYREF
  int v26; // [rsp+108h] [rbp-18h]
  _DWORD *v27; // [rsp+110h] [rbp-10h] BYREF
  int v28; // [rsp+118h] [rbp-8h]
  _DWORD *v29; // [rsp+120h] [rbp+0h] BYREF
  int v30; // [rsp+128h] [rbp+8h]
  __int64 v31; // [rsp+130h] [rbp+10h] BYREF
  int v32; // [rsp+138h] [rbp+18h]
  _DWORD v33[32]; // [rsp+140h] [rbp+20h] BYREF
  _DWORD v34[32]; // [rsp+1C0h] [rbp+A0h] BYREF

  v31 = 0;
  v32 = 0;
  v34[0] = 3;
  memset(&v34[1], 0, 0x70u);
  v33[0] = 3;
  memset(&v33[1], 0, 0x70u);
  SpAcquireResourceShared((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96), 0);
  SP_DEVICE::AcquireMutex((SP_DEVICE *)this);
  v2 = this[403];
  if ( v2 )
  {
    SP_SPACE::GetHealth(this[403], (struct _SIO_HEALTH_CONTEXT *)v33);
    updated = SIO_SPACE::UpdateColumnState(v2, (struct _SIO_UPDATE_COLUMN_CONTEXT *)&v31);
    if ( updated >= 0 )
    {
      SP_SPACE::GetHealth(v2, (struct _SIO_HEALTH_CONTEXT *)v34);
      if ( (_BYTE)v31 )
        SpSpaceRequestRepair((struct _GUID *)((char *)v2 + 24));
      v4 = 1;
      if ( BYTE1(v31) )
      {
        *(_WORD *)(*((_QWORD *)v2 + 145) + 472LL) |= 1u;
        SpaceById = SDB_POOL_CONFIG::FindSpaceById(*((SDB_POOL_CONFIG **)v2 + 18), (struct _GUID *)((char *)v2 + 24));
        _InterlockedOr16(
          (volatile signed __int16 *)(*((_QWORD *)SpaceById + (*((_WORD *)SpaceById + 15) & 1LL) + 4) + 352LL),
          2u);
        SP_WORKITEM::Insert((char *)WPP_MAIN_CB.DeviceExtension + 1824, 0, 0, 0);
      }
      if ( BYTE2(v31) )
        SP_WORKITEM::Insert(
          (PVOID)(*((_QWORD *)v2 + 144) + 512LL),
          0,
          1000 * *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 119),
          0);
      if ( v33[5] || v33[6] || (v6 = 3, v33[8]) )
        v6 = 1;
      v33[0] = v6;
      if ( v34[5] || v34[6] || v34[8] )
      {
        v34[0] = 1;
      }
      else
      {
        v4 = 3;
        v34[0] = 3;
      }
      if ( v6 != v4
        && (unsigned int)dword_14007F050 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
      {
        v10 = 3;
        v20 = 36;
        v19 = &v33[20];
        v21 = &v33[11];
        v23 = &v33[3];
        v11 = v33[2];
        v12 = v33[1];
        v13 = v33[0];
        v25 = &v34[20];
        v27 = &v34[11];
        v29 = &v34[3];
        v14 = v34[2];
        v15 = v34[1];
        v16 = v34[0];
        v17 = (char *)v2 + 24;
        v18 = (char *)v2 + 8;
        v22 = 36;
        v26 = 36;
        v28 = 36;
        v24 = 32;
        v30 = 32;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>>(
          32,
          (unsigned int)byte_1400760A5,
          v7,
          v8,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&v16,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v29,
          (__int64)&v27,
          (__int64)&v25,
          (__int64)&v13,
          (__int64)&v12,
          (__int64)&v11,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v19,
          (__int64)&v10);
      }
    }
  }
  else
  {
    updated = -1073741810;
  }
  SP_DEVICE::ReleaseMutex((SP_DEVICE *)this);
  ExReleaseResourceLite((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  KeLeaveCriticalRegion();
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14003c6b8  push    rbp
0x14003c6ba  push    rbx
0x14003c6bb  push    rsi
0x14003c6bc  push    rdi
0x14003c6bd  push    r12
0x14003c6bf  push    r14
0x14003c6c1  lea     rbp, [rsp-138h]
0x14003c6c9  sub     rsp, 258h
0x14003c6d0  mov     rax, cs:__security_cookie
0x14003c6d7  xor     rax, rsp
0x14003c6da  mov     [rbp+160h+var_40], rax
0x14003c6e1  xor     eax, eax
0x14003c6e3  mov     r14, rcx
0x14003c6e6  xor     edx, edx; Val
0x14003c6e8  mov     [rbp+160h+var_150], rax
0x14003c6ec  lea     rcx, [rbp+160h+var_BC]; void *
0x14003c6f3  mov     [rbp+160h+var_148], eax
0x14003c6f6  lea     ebx, [rax+70h]
0x14003c6f9  lea     r12d, [rax+3]
0x14003c6fd  mov     r8d, ebx; Size
0x14003c700  mov     [rbp+160h+var_C0], r12d
0x14003c707  call    memset
0x14003c70c  mov     r8d, ebx; Size
0x14003c70f  mov     [rbp+160h+var_140], r12d
0x14003c713  xor     edx, edx; Val
0x14003c715  lea     rcx, [rbp+160h+var_13C]; void *
0x14003c719  call    memset
0x14003c71e  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003c725  xor     edx, edx; unsigned __int8
0x14003c727  add     rcx, 60h ; '`'; Resource
0x14003c72b  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x14003c730  mov     rcx, r14; this
0x14003c733  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x14003c738  mov     rbx, [r14+0C98h]
0x14003c73f  test    rbx, rbx
0x14003c742  jnz     short loc_14003C74E
0x14003c744  mov     esi, 0C000000Eh
0x14003c749  jmp     loc_14003C9C3
0x14003c74e  lea     rdx, [rbp+160h+var_140]; struct _SIO_HEALTH_CONTEXT *
0x14003c752  mov     rcx, rbx; this
0x14003c755  call    ?GetHealth@SP_SPACE@@QEAAJPEAU_SIO_HEALTH_CONTEXT@@@Z; SP_SPACE::GetHealth(_SIO_HEALTH_CONTEXT *)
0x14003c75a  lea     rdx, [rbp+160h+var_150]; struct _SIO_UPDATE_COLUMN_CONTEXT *
0x14003c75e  mov     rcx, rbx; this
0x14003c761  call    ?UpdateColumnState@SIO_SPACE@@QEAAJPEAU_SIO_UPDATE_COLUMN_CONTEXT@@@Z; SIO_SPACE::UpdateColumnState(_SIO_UPDATE_COLUMN_CONTEXT *)
0x14003c766  mov     esi, eax
0x14003c768  test    eax, eax
0x14003c76a  js      loc_14003C9C3
0x14003c770  lea     rdx, [rbp+160h+var_C0]; struct _SIO_HEALTH_CONTEXT *
0x14003c777  mov     rcx, rbx; this
0x14003c77a  call    ?GetHealth@SP_SPACE@@QEAAJPEAU_SIO_HEALTH_CONTEXT@@@Z; SP_SPACE::GetHealth(_SIO_HEALTH_CONTEXT *)
0x14003c77f  cmp     byte ptr [rbp+160h+var_150], 0
0x14003c783  jz      short loc_14003C78E
0x14003c785  lea     rcx, [rbx+18h]; struct _GUID *
0x14003c789  call    ?SpSpaceRequestRepair@@YAXPEAU_GUID@@@Z; SpSpaceRequestRepair(_GUID *)
0x14003c78e  cmp     byte ptr [rbp+160h+var_150+1], 0
0x14003c792  mov     edi, 1
0x14003c797  jz      short loc_14003C7E7
0x14003c799  mov     rax, [rbx+488h]
0x14003c7a0  lea     rdx, [rbx+18h]; struct _GUID *
0x14003c7a4  or      [rax+1D8h], di
0x14003c7ab  mov     rcx, [rbx+90h]; this
0x14003c7b2  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x14003c7b7  movzx   ecx, word ptr [rax+1Eh]
0x14003c7bb  and     rcx, rdi
0x14003c7be  mov     rdx, [rax+rcx*8+20h]
0x14003c7c3  lock or word ptr [rdx+160h], 2
0x14003c7cc  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003c7d3  xor     r9d, r9d; unsigned __int8
0x14003c7d6  add     rcx, 720h; Context
0x14003c7dd  xor     r8d, r8d; unsigned int
0x14003c7e0  xor     edx, edx; struct _LIST_ENTRY *
0x14003c7e2  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14003c7e7  cmp     byte ptr [rbp+160h+var_150+2], 0
0x14003c7eb  jz      short loc_14003C817
0x14003c7ed  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003c7f4  xor     r9d, r9d; unsigned __int8
0x14003c7f7  mov     rcx, [rbx+480h]
0x14003c7fe  xor     edx, edx; struct _LIST_ENTRY *
0x14003c800  add     rcx, 200h; Context
0x14003c807  imul    r8d, [rax+1DCh], 3E8h; unsigned int
0x14003c812  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14003c817  cmp     [rbp+160h+var_12C], 0
0x14003c81b  ja      short loc_14003C82C
0x14003c81d  cmp     [rbp+160h+var_128], 0
0x14003c821  ja      short loc_14003C82C
0x14003c823  cmp     [rbp+160h+var_120], 0
0x14003c827  mov     eax, r12d
0x14003c82a  jbe     short loc_14003C82E
0x14003c82c  mov     eax, edi
0x14003c82e  cmp     [rbp+160h+var_AC], 0
0x14003c835  mov     [rbp+160h+var_140], eax
0x14003c838  ja      short loc_14003C858
0x14003c83a  cmp     [rbp+160h+var_A8], 0
0x14003c841  ja      short loc_14003C858
0x14003c843  cmp     [rbp+160h+var_A0], 0
0x14003c84a  ja      short loc_14003C858
0x14003c84c  mov     edi, r12d
0x14003c84f  mov     [rbp+160h+var_C0], r12d
0x14003c856  jmp     short loc_14003C85E
0x14003c858  mov     [rbp+160h+var_C0], edi
0x14003c85e  cmp     eax, edi
0x14003c860  jz      loc_14003C9C3
0x14003c866  mov     eax, cs:dword_14007F050
0x14003c86c  cmp     eax, 5
0x14003c86f  jbe     loc_14003C9C3
0x14003c875  mov     rdx, 400000000000h
0x14003c87f  lea     rcx, dword_14007F050
0x14003c886  call    _tlgKeywordOn
0x14003c88b  test    al, al
0x14003c88d  jz      loc_14003C9C3
0x14003c893  mov     edx, 24h ; '$'
0x14003c898  mov     [rbp+160h+var_1E0], r12d
0x14003c89c  lea     rax, [rbp+160h+var_F0]
0x14003c8a0  mov     [rbp+160h+var_1A8], edx
0x14003c8a3  mov     [rbp+160h+var_1B0], rax
0x14003c8a7  lea     rax, [rbp+160h+var_114]
0x14003c8ab  mov     [rbp+160h+var_1A0], rax
0x14003c8af  lea     rax, [rbp+160h+var_134]
0x14003c8b3  mov     [rbp+160h+var_190], rax
0x14003c8b7  lea     ecx, [rdx-4]
0x14003c8ba  mov     eax, [rbp+160h+var_138]
0x14003c8bd  mov     [rbp+160h+var_1DC], eax
0x14003c8c0  mov     eax, [rbp+160h+var_13C]
0x14003c8c3  mov     [rbp+160h+var_1D8], eax
0x14003c8c6  mov     eax, [rbp+160h+var_140]
0x14003c8c9  mov     [rbp+160h+var_1D4], eax
0x14003c8cc  lea     rax, [rbp+160h+var_70]
0x14003c8d3  mov     [rbp+160h+var_180], rax
0x14003c8d7  lea     rax, [rbp+160h+var_94]
0x14003c8de  mov     [rbp+160h+var_170], rax
0x14003c8e2  lea     rax, [rbp+160h+var_B4]
0x14003c8e9  mov     [rbp+160h+var_160], rax
0x14003c8ed  mov     eax, [rbp+160h+var_B8]
0x14003c8f3  mov     [rbp+160h+var_1D0], eax
0x14003c8f6  mov     eax, [rbp+160h+var_BC]
0x14003c8fc  mov     [rbp+160h+var_1CC], eax
0x14003c8ff  mov     eax, [rbp+160h+var_C0]
0x14003c905  mov     [rbp+160h+var_1C8], eax
0x14003c908  lea     rax, [rbx+18h]
0x14003c90c  mov     [rbp+160h+var_1C0], rax
0x14003c910  lea     rax, [rbx+8]
0x14003c914  mov     [rbp+160h+var_1B8], rax
0x14003c918  lea     rax, [rbp+160h+var_1E0]
0x14003c91c  mov     [rsp+280h+var_1F0], rax
0x14003c924  lea     rax, [rbp+160h+var_1B0]
0x14003c928  mov     [rsp+280h+var_1F8], rax
0x14003c930  lea     rax, [rbp+160h+var_1A0]
0x14003c934  mov     [rsp+280h+var_200], rax
0x14003c93c  lea     rax, [rbp+160h+var_190]
0x14003c940  mov     [rsp+280h+var_208], rax
0x14003c945  lea     rax, [rbp+160h+var_1DC]
0x14003c949  mov     [rsp+280h+var_210], rax
0x14003c94e  lea     rax, [rbp+160h+var_1D8]
0x14003c952  mov     [rsp+280h+var_218], rax
0x14003c957  lea     rax, [rbp+160h+var_1D4]
0x14003c95b  mov     [rsp+280h+var_220], rax
0x14003c960  lea     rax, [rbp+160h+var_180]
0x14003c964  mov     [rsp+280h+var_228], rax
0x14003c969  lea     rax, [rbp+160h+var_170]
0x14003c96d  mov     [rsp+280h+var_230], rax
0x14003c972  lea     rax, [rbp+160h+var_160]
0x14003c976  mov     [rsp+280h+var_238], rax
0x14003c97b  lea     rax, [rbp+160h+var_1D0]
0x14003c97f  mov     [rsp+280h+var_240], rax
0x14003c984  lea     rax, [rbp+160h+var_1CC]
0x14003c988  mov     [rsp+280h+var_248], rax
0x14003c98d  lea     rax, [rbp+160h+var_1C8]
0x14003c991  mov     [rsp+280h+var_250], rax
0x14003c996  lea     rax, [rbp+160h+var_1C0]
0x14003c99a  mov     [rsp+280h+var_258], rax
0x14003c99f  lea     rax, [rbp+160h+var_1B8]
0x14003c9a3  mov     [rbp+160h+var_198], edx
0x14003c9a6  mov     [rbp+160h+var_178], edx
0x14003c9a9  mov     [rbp+160h+var_168], edx
0x14003c9ac  lea     rdx, byte_1400760A5
0x14003c9b3  mov     [rsp+280h+var_260], rax
0x14003c9b8  mov     [rbp+160h+var_188], ecx
0x14003c9bb  mov     [rbp+160h+var_158], ecx
0x14003c9be  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U_tlgWrapperPtrSize@@U3@U3@U2@U2@U2@U3@U3@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU_tlgWrapperPtrSize@@554445554@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &)
0x14003c9c3  mov     rcx, r14; this
0x14003c9c6  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x14003c9cb  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003c9d2  add     rcx, 60h ; '`'; Resource
0x14003c9d6  call    cs:__imp_ExReleaseResourceLite
0x14003c9dd  nop     dword ptr [rax+rax+00h]
0x14003c9e2  call    cs:__imp_KeLeaveCriticalRegion
0x14003c9e9  nop     dword ptr [rax+rax+00h]
0x14003c9ee  mov     eax, esi
0x14003c9f0  mov     rcx, [rbp+160h+var_40]
0x14003c9f7  xor     rcx, rsp; StackCookie
0x14003c9fa  call    __security_check_cookie
0x14003c9ff  add     rsp, 258h
0x14003ca06  pop     r14
0x14003ca08  pop     r12
0x14003ca0a  pop     rdi
0x14003ca0b  pop     rsi
0x14003ca0c  pop     rbx
0x14003ca0d  pop     rbp
0x14003ca0e  retn
```
