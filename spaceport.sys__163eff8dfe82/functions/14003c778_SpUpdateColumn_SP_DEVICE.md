# SpUpdateColumn(SP_DEVICE *)

- ea: `0x14003c778`
- end: `0x14003cad0`
- name: `?SpUpdateColumn@@YAJPEAVSP_DEVICE@@@Z`
- size: `856`
- prototype: `__int64 __fastcall(struct SP_DEVICE *this)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14002b360`
- `0x14002b608`
- `0x14003cae0`

## callees

- `0x14000200c`
- `0x1400034dc`
- `0x14000b3e0`
- `0x140011970`
- `0x14001d3f0`
- `0x1400216f0`
- `0x140021a90`
- `0x14003c6c4`
- `0x14003c778`
- `0x140043a74`
- `0x140068110`
- `0x140068600`
- `0x1400b58c0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003caa2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003caa2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ca96`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ca96`

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
0x14003c778  push    rbp
0x14003c77a  push    rbx
0x14003c77b  push    rsi
0x14003c77c  push    rdi
0x14003c77d  push    r12
0x14003c77f  push    r14
0x14003c781  lea     rbp, [rsp-138h]
0x14003c789  sub     rsp, 258h
0x14003c790  mov     rax, cs:__security_cookie
0x14003c797  xor     rax, rsp
0x14003c79a  mov     [rbp+160h+var_40], rax
0x14003c7a1  xor     eax, eax
0x14003c7a3  mov     r14, rcx
0x14003c7a6  xor     edx, edx; Val
0x14003c7a8  mov     [rbp+160h+var_150], rax
0x14003c7ac  lea     rcx, [rbp+160h+var_BC]; void *
0x14003c7b3  mov     [rbp+160h+var_148], eax
0x14003c7b6  lea     ebx, [rax+70h]
0x14003c7b9  lea     r12d, [rax+3]
0x14003c7bd  mov     r8d, ebx; Size
0x14003c7c0  mov     [rbp+160h+var_C0], r12d
0x14003c7c7  call    memset
0x14003c7cc  mov     r8d, ebx; Size
0x14003c7cf  mov     [rbp+160h+var_140], r12d
0x14003c7d3  xor     edx, edx; Val
0x14003c7d5  lea     rcx, [rbp+160h+var_13C]; void *
0x14003c7d9  call    memset
0x14003c7de  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003c7e5  xor     edx, edx; unsigned __int8
0x14003c7e7  add     rcx, 60h ; '`'; Resource
0x14003c7eb  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x14003c7f0  mov     rcx, r14; this
0x14003c7f3  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x14003c7f8  mov     rbx, [r14+0C98h]
0x14003c7ff  test    rbx, rbx
0x14003c802  jnz     short loc_14003C80E
0x14003c804  mov     esi, 0C000000Eh
0x14003c809  jmp     loc_14003CA83
0x14003c80e  lea     rdx, [rbp+160h+var_140]; struct _SIO_HEALTH_CONTEXT *
0x14003c812  mov     rcx, rbx; this
0x14003c815  call    ?GetHealth@SP_SPACE@@QEAAJPEAU_SIO_HEALTH_CONTEXT@@@Z; SP_SPACE::GetHealth(_SIO_HEALTH_CONTEXT *)
0x14003c81a  lea     rdx, [rbp+160h+var_150]; struct _SIO_UPDATE_COLUMN_CONTEXT *
0x14003c81e  mov     rcx, rbx; this
0x14003c821  call    ?UpdateColumnState@SIO_SPACE@@QEAAJPEAU_SIO_UPDATE_COLUMN_CONTEXT@@@Z; SIO_SPACE::UpdateColumnState(_SIO_UPDATE_COLUMN_CONTEXT *)
0x14003c826  mov     esi, eax
0x14003c828  test    eax, eax
0x14003c82a  js      loc_14003CA83
0x14003c830  lea     rdx, [rbp+160h+var_C0]; struct _SIO_HEALTH_CONTEXT *
0x14003c837  mov     rcx, rbx; this
0x14003c83a  call    ?GetHealth@SP_SPACE@@QEAAJPEAU_SIO_HEALTH_CONTEXT@@@Z; SP_SPACE::GetHealth(_SIO_HEALTH_CONTEXT *)
0x14003c83f  cmp     byte ptr [rbp+160h+var_150], 0
0x14003c843  jz      short loc_14003C84E
0x14003c845  lea     rcx, [rbx+18h]; struct _GUID *
0x14003c849  call    ?SpSpaceRequestRepair@@YAXPEAU_GUID@@@Z; SpSpaceRequestRepair(_GUID *)
0x14003c84e  cmp     byte ptr [rbp+160h+var_150+1], 0
0x14003c852  mov     edi, 1
0x14003c857  jz      short loc_14003C8A7
0x14003c859  mov     rax, [rbx+488h]
0x14003c860  lea     rdx, [rbx+18h]; struct _GUID *
0x14003c864  or      [rax+1D8h], di
0x14003c86b  mov     rcx, [rbx+90h]; this
0x14003c872  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x14003c877  movzx   ecx, word ptr [rax+1Eh]
0x14003c87b  and     rcx, rdi
0x14003c87e  mov     rdx, [rax+rcx*8+20h]
0x14003c883  lock or word ptr [rdx+160h], 2
0x14003c88c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003c893  xor     r9d, r9d; unsigned __int8
0x14003c896  add     rcx, 720h; Context
0x14003c89d  xor     r8d, r8d; unsigned int
0x14003c8a0  xor     edx, edx; struct _LIST_ENTRY *
0x14003c8a2  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14003c8a7  cmp     byte ptr [rbp+160h+var_150+2], 0
0x14003c8ab  jz      short loc_14003C8D7
0x14003c8ad  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003c8b4  xor     r9d, r9d; unsigned __int8
0x14003c8b7  mov     rcx, [rbx+480h]
0x14003c8be  xor     edx, edx; struct _LIST_ENTRY *
0x14003c8c0  add     rcx, 200h; Context
0x14003c8c7  imul    r8d, [rax+1DCh], 3E8h; unsigned int
0x14003c8d2  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14003c8d7  cmp     [rbp+160h+var_12C], 0
0x14003c8db  ja      short loc_14003C8EC
0x14003c8dd  cmp     [rbp+160h+var_128], 0
0x14003c8e1  ja      short loc_14003C8EC
0x14003c8e3  cmp     [rbp+160h+var_120], 0
0x14003c8e7  mov     eax, r12d
0x14003c8ea  jbe     short loc_14003C8EE
0x14003c8ec  mov     eax, edi
0x14003c8ee  cmp     [rbp+160h+var_AC], 0
0x14003c8f5  mov     [rbp+160h+var_140], eax
0x14003c8f8  ja      short loc_14003C918
0x14003c8fa  cmp     [rbp+160h+var_A8], 0
0x14003c901  ja      short loc_14003C918
0x14003c903  cmp     [rbp+160h+var_A0], 0
0x14003c90a  ja      short loc_14003C918
0x14003c90c  mov     edi, r12d
0x14003c90f  mov     [rbp+160h+var_C0], r12d
0x14003c916  jmp     short loc_14003C91E
0x14003c918  mov     [rbp+160h+var_C0], edi
0x14003c91e  cmp     eax, edi
0x14003c920  jz      loc_14003CA83
0x14003c926  mov     eax, cs:dword_14007F050
0x14003c92c  cmp     eax, 5
0x14003c92f  jbe     loc_14003CA83
0x14003c935  mov     rdx, 400000000000h
0x14003c93f  lea     rcx, dword_14007F050
0x14003c946  call    _tlgKeywordOn
0x14003c94b  test    al, al
0x14003c94d  jz      loc_14003CA83
0x14003c953  mov     edx, 24h ; '$'
0x14003c958  mov     [rbp+160h+var_1E0], r12d
0x14003c95c  lea     rax, [rbp+160h+var_F0]
0x14003c960  mov     [rbp+160h+var_1A8], edx
0x14003c963  mov     [rbp+160h+var_1B0], rax
0x14003c967  lea     rax, [rbp+160h+var_114]
0x14003c96b  mov     [rbp+160h+var_1A0], rax
0x14003c96f  lea     rax, [rbp+160h+var_134]
0x14003c973  mov     [rbp+160h+var_190], rax
0x14003c977  lea     ecx, [rdx-4]
0x14003c97a  mov     eax, [rbp+160h+var_138]
0x14003c97d  mov     [rbp+160h+var_1DC], eax
0x14003c980  mov     eax, [rbp+160h+var_13C]
0x14003c983  mov     [rbp+160h+var_1D8], eax
0x14003c986  mov     eax, [rbp+160h+var_140]
0x14003c989  mov     [rbp+160h+var_1D4], eax
0x14003c98c  lea     rax, [rbp+160h+var_70]
0x14003c993  mov     [rbp+160h+var_180], rax
0x14003c997  lea     rax, [rbp+160h+var_94]
0x14003c99e  mov     [rbp+160h+var_170], rax
0x14003c9a2  lea     rax, [rbp+160h+var_B4]
0x14003c9a9  mov     [rbp+160h+var_160], rax
0x14003c9ad  mov     eax, [rbp+160h+var_B8]
0x14003c9b3  mov     [rbp+160h+var_1D0], eax
0x14003c9b6  mov     eax, [rbp+160h+var_BC]
0x14003c9bc  mov     [rbp+160h+var_1CC], eax
0x14003c9bf  mov     eax, [rbp+160h+var_C0]
0x14003c9c5  mov     [rbp+160h+var_1C8], eax
0x14003c9c8  lea     rax, [rbx+18h]
0x14003c9cc  mov     [rbp+160h+var_1C0], rax
0x14003c9d0  lea     rax, [rbx+8]
0x14003c9d4  mov     [rbp+160h+var_1B8], rax
0x14003c9d8  lea     rax, [rbp+160h+var_1E0]
0x14003c9dc  mov     [rsp+280h+var_1F0], rax
0x14003c9e4  lea     rax, [rbp+160h+var_1B0]
0x14003c9e8  mov     [rsp+280h+var_1F8], rax
0x14003c9f0  lea     rax, [rbp+160h+var_1A0]
0x14003c9f4  mov     [rsp+280h+var_200], rax
0x14003c9fc  lea     rax, [rbp+160h+var_190]
0x14003ca00  mov     [rsp+280h+var_208], rax
0x14003ca05  lea     rax, [rbp+160h+var_1DC]
0x14003ca09  mov     [rsp+280h+var_210], rax
0x14003ca0e  lea     rax, [rbp+160h+var_1D8]
0x14003ca12  mov     [rsp+280h+var_218], rax
0x14003ca17  lea     rax, [rbp+160h+var_1D4]
0x14003ca1b  mov     [rsp+280h+var_220], rax
0x14003ca20  lea     rax, [rbp+160h+var_180]
0x14003ca24  mov     [rsp+280h+var_228], rax
0x14003ca29  lea     rax, [rbp+160h+var_170]
0x14003ca2d  mov     [rsp+280h+var_230], rax
0x14003ca32  lea     rax, [rbp+160h+var_160]
0x14003ca36  mov     [rsp+280h+var_238], rax
0x14003ca3b  lea     rax, [rbp+160h+var_1D0]
0x14003ca3f  mov     [rsp+280h+var_240], rax
0x14003ca44  lea     rax, [rbp+160h+var_1CC]
0x14003ca48  mov     [rsp+280h+var_248], rax
0x14003ca4d  lea     rax, [rbp+160h+var_1C8]
0x14003ca51  mov     [rsp+280h+var_250], rax
0x14003ca56  lea     rax, [rbp+160h+var_1C0]
0x14003ca5a  mov     [rsp+280h+var_258], rax
0x14003ca5f  lea     rax, [rbp+160h+var_1B8]
0x14003ca63  mov     [rbp+160h+var_198], edx
0x14003ca66  mov     [rbp+160h+var_178], edx
0x14003ca69  mov     [rbp+160h+var_168], edx
0x14003ca6c  lea     rdx, byte_1400760A5
0x14003ca73  mov     [rsp+280h+var_260], rax
0x14003ca78  mov     [rbp+160h+var_188], ecx
0x14003ca7b  mov     [rbp+160h+var_158], ecx
0x14003ca7e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U_tlgWrapperPtrSize@@U3@U3@U2@U2@U2@U3@U3@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU_tlgWrapperPtrSize@@554445554@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &)
0x14003ca83  mov     rcx, r14; this
0x14003ca86  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x14003ca8b  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003ca92  add     rcx, 60h ; '`'; Resource
0x14003ca96  call    cs:__imp_ExReleaseResourceLite
0x14003ca9d  nop     dword ptr [rax+rax+00h]
0x14003caa2  call    cs:__imp_KeLeaveCriticalRegion
0x14003caa9  nop     dword ptr [rax+rax+00h]
0x14003caae  mov     eax, esi
0x14003cab0  mov     rcx, [rbp+160h+var_40]
0x14003cab7  xor     rcx, rsp; StackCookie
0x14003caba  call    __security_check_cookie
0x14003cabf  add     rsp, 258h
0x14003cac6  pop     r14
0x14003cac8  pop     r12
0x14003caca  pop     rdi
0x14003cacb  pop     rsi
0x14003cacc  pop     rbx
0x14003cacd  pop     rbp
0x14003cace  retn
```
