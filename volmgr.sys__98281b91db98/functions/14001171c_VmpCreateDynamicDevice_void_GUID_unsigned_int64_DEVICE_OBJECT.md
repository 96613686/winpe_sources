# VmpCreateDynamicDevice(void *,_GUID *,unsigned __int64,_DEVICE_OBJECT * *)

- ea: `0x14001171c`
- end: `0x140011919`
- name: `?VmpCreateDynamicDevice@@YAJPEAXPEAU_GUID@@_KPEAPEAU_DEVICE_OBJECT@@@Z`
- size: `509`
- prototype: `int(void *, struct _GUID *, unsigned __int64, struct _DEVICE_OBJECT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f950`

## callees

- `0x140001328`
- `0x1400013e8`
- `0x140003e70`
- `0x140005090`
- `0x1400114f8`
- `0x14001171c`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400118f1`
- `ntoskrnl!IoDeleteDevice` at `0x1400118f1`

## pseudocode

```c
__int64 __fastcall VmpCreateDynamicDevice(void *a1, struct _DEVICE_OBJECT *a2, __int64 a3, struct _DEVICE_OBJECT **a4)
{
  int v7; // eax
  PDEVICE_OBJECT v8; // rbx
  unsigned int v9; // r14d
  _BYTE *DeviceExtension; // rdi
  struct VM_ROOT_EXTENSION *v11; // rcx
  __int64 v12; // r13
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  bool v16; // al
  struct VM_ROOT_EXTENSION *v17; // rcx
  char v19; // [rsp+50h] [rbp-10h] BYREF
  bool v20; // [rsp+51h] [rbp-Fh] BYREF
  char v21; // [rsp+52h] [rbp-Eh] BYREF
  char v22; // [rsp+53h] [rbp-Dh] BYREF
  char v23; // [rsp+54h] [rbp-Ch] BYREF
  char v24[3]; // [rsp+55h] [rbp-Bh] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+58h] [rbp-8h] BYREF
  char v26; // [rsp+B0h] [rbp+50h] BYREF
  char v27; // [rsp+B8h] [rbp+58h] BYREF

  *a4 = 0;
  v19 = 0;
  v26 = 0;
  DeviceObject = 0;
  v27 = 0;
  v7 = VmpCreateDeviceObject(0, a3, (a3 & 0x4000000000000000LL) != 0, &DeviceObject);
  v8 = DeviceObject;
  v9 = v7;
  if ( v7 >= 0 )
  {
    DeviceExtension = DeviceObject->DeviceExtension;
    v11 = VmRootExtension;
    DeviceExtension[426] = 1;
    *((_QWORD *)DeviceExtension + 54) = a1;
    v12 = *((_QWORD *)v11 + 49);
    (*(void (__fastcall **)(void *, char *, char *, char *))(v12 + 144))(a1, &v27, &v19, &v26);
    if ( v27 )
      v8->Flags |= 0x200000u;
    if ( v19 )
      v8->Flags |= 0x100u;
    if ( v26 )
      v8->Flags |= 0x400000u;
    if ( (*(_DWORD *)(*(_QWORD *)DeviceExtension + 48LL) & 0x600100) != 0 || *((_DWORD *)DeviceExtension + 37) )
      DeviceExtension[160] = 0;
    v8->AlignmentRequirement = (*(__int64 (__fastcall **)(_QWORD))(v12 + 136))(*((_QWORD *)DeviceExtension + 54));
    v8->StackSize = (*(__int64 (__fastcall **)(_QWORD))(v12 + 128))(*((_QWORD *)DeviceExtension + 54)) + 2;
    (*(void (__fastcall **)(_QWORD, _BYTE *))(v12 + 120))(*((_QWORD *)DeviceExtension + 54), DeviceExtension + 408);
    v8->Flags &= ~0x80u;
    if ( (unsigned int)dword_14000A048 > 5 && (unsigned __int8)tlgKeywordOn() )
    {
      v16 = (*((_QWORD *)DeviceExtension + 39) & 0x1000000000000000LL) != 0;
      DeviceObject = a2;
      v20 = v16;
      v21 = DeviceExtension[152];
      v22 = v26;
      v23 = v27;
      v24[0] = v19;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        v13,
        (unsigned int)&dword_14000815C,
        v14,
        v15,
        (__int64)&DeviceObject,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v20);
    }
    v17 = VmRootExtension;
    *a4 = v8;
    v8 = 0;
    VmpRestoreExtensionDriver(v17);
  }
  if ( v8 )
    IoDeleteDevice(v8);
  return v9;
}

```

## disassembly

```asm
0x14001171c  mov     [rsp-38h+arg_0], rbx
0x140011721  push    rbp
0x140011722  push    rsi
0x140011723  push    rdi
0x140011724  push    r12
0x140011726  push    r13
0x140011728  push    r14
0x14001172a  push    r15
0x14001172c  mov     rbp, rsp
0x14001172f  sub     rsp, 60h
0x140011733  xor     ebx, ebx
0x140011735  mov     rax, r8
0x140011738  shr     r8, 3Eh
0x14001173c  mov     r15, r9
0x14001173f  mov     [r9], rbx
0x140011742  mov     r12, rdx
0x140011745  mov     rsi, rcx
0x140011748  mov     [rbp+var_10], bl
0x14001174b  and     r8b, 1; unsigned __int8
0x14001174f  mov     [rbp+arg_10], bl
0x140011752  lea     r9, [rbp+DeviceObject]; struct _DEVICE_OBJECT **
0x140011756  mov     [rbp+DeviceObject], rbx
0x14001175a  mov     rdx, rax; unsigned __int64
0x14001175d  mov     [rbp+arg_18], bl
0x140011760  xor     ecx, ecx; unsigned int
0x140011762  call    ?VmpCreateDeviceObject@@YAJK_KEPEAPEAU_DEVICE_OBJECT@@@Z; VmpCreateDeviceObject(ulong,unsigned __int64,uchar,_DEVICE_OBJECT * *)
0x140011767  mov     rbx, [rbp+DeviceObject]
0x14001176b  mov     r14d, eax
0x14001176e  test    eax, eax
0x140011770  js      loc_1400118E9
0x140011776  mov     rdi, [rbx+40h]
0x14001177a  lea     r9, [rbp+arg_10]
0x14001177e  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140011785  lea     r8, [rbp+var_10]
0x140011789  lea     rdx, [rbp+arg_18]
0x14001178d  mov     byte ptr [rdi+1AAh], 1
0x140011794  mov     [rdi+1B0h], rsi
0x14001179b  mov     r13, [rcx+188h]
0x1400117a2  mov     rcx, rsi
0x1400117a5  mov     rax, [r13+90h]
0x1400117ac  call    _guard_dispatch_icall
0x1400117b1  xor     esi, esi
0x1400117b3  cmp     [rbp+arg_18], sil
0x1400117b7  jz      short loc_1400117C3
0x1400117b9  mov     eax, [rbx+30h]
0x1400117bc  bts     eax, 15h
0x1400117c0  mov     [rbx+30h], eax
0x1400117c3  cmp     [rbp+var_10], sil
0x1400117c7  jz      short loc_1400117D3
0x1400117c9  mov     eax, [rbx+30h]
0x1400117cc  bts     eax, 8
0x1400117d0  mov     [rbx+30h], eax
0x1400117d3  cmp     [rbp+arg_10], sil
0x1400117d7  jz      short loc_1400117E3
0x1400117d9  mov     eax, [rbx+30h]
0x1400117dc  bts     eax, 16h
0x1400117e0  mov     [rbx+30h], eax
0x1400117e3  mov     rax, [rdi]
0x1400117e6  mov     ecx, [rax+30h]
0x1400117e9  test    ecx, 600100h
0x1400117ef  jnz     short loc_1400117F9
0x1400117f1  cmp     [rdi+94h], esi
0x1400117f7  jz      short loc_140011800
0x1400117f9  mov     [rdi+0A0h], sil
0x140011800  mov     rax, [r13+88h]
0x140011807  mov     rcx, [rdi+1B0h]
0x14001180e  call    _guard_dispatch_icall
0x140011813  mov     [rbx+98h], eax
0x140011819  mov     rax, [r13+80h]
0x140011820  mov     rcx, [rdi+1B0h]
0x140011827  call    _guard_dispatch_icall
0x14001182c  add     al, 2
0x14001182e  lea     rdx, [rdi+198h]
0x140011835  mov     [rbx+4Ch], al
0x140011838  mov     rax, [r13+78h]
0x14001183c  mov     rcx, [rdi+1B0h]
0x140011843  call    _guard_dispatch_icall
0x140011848  mov     eax, [rbx+30h]
0x14001184b  btr     eax, 7
0x14001184f  mov     [rbx+30h], eax
0x140011852  mov     eax, cs:dword_14000A048
0x140011858  cmp     eax, 5
0x14001185b  jbe     short loc_1400118D7
0x14001185d  call    _tlgKeywordOn
0x140011862  test    al, al
0x140011864  jz      short loc_1400118D7
0x140011866  mov     rax, [rdi+138h]
0x14001186d  lea     rdx, dword_14000815C
0x140011874  shr     rax, 3Ch
0x140011878  and     al, 1
0x14001187a  mov     [rbp+DeviceObject], r12
0x14001187e  mov     [rbp+var_F], al
0x140011881  mov     al, [rdi+98h]
0x140011887  mov     [rbp+var_E], al
0x14001188a  mov     al, [rbp+arg_10]
0x14001188d  mov     [rbp+var_D], al
0x140011890  mov     al, [rbp+arg_18]
0x140011893  mov     [rbp+var_C], al
0x140011896  mov     al, [rbp+var_10]
0x140011899  mov     [rbp+var_B], al
0x14001189c  lea     rax, [rbp+var_F]
0x1400118a0  mov     [rsp+60h+var_18], rax
0x1400118a5  lea     rax, [rbp+var_E]
0x1400118a9  mov     [rsp+60h+var_20], rax
0x1400118ae  lea     rax, [rbp+var_D]
0x1400118b2  mov     [rsp+60h+var_28], rax
0x1400118b7  lea     rax, [rbp+var_C]
0x1400118bb  mov     [rsp+60h+var_30], rax
0x1400118c0  lea     rax, [rbp+var_B]
0x1400118c4  mov     [rsp+60h+var_38], rax
0x1400118c9  lea     rax, [rbp+DeviceObject]
0x1400118cd  mov     [rsp+60h+var_40], rax
0x1400118d2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x1400118d7  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400118de  mov     [r15], rbx
0x1400118e1  mov     rbx, rsi
0x1400118e4  call    VmpRestoreExtensionDriver
0x1400118e9  test    rbx, rbx
0x1400118ec  jz      short loc_1400118FD
0x1400118ee  mov     rcx, rbx; DeviceObject
0x1400118f1  call    cs:__imp_IoDeleteDevice
0x1400118f8  nop     dword ptr [rax+rax+00h]
0x1400118fd  mov     rbx, [rsp+60h+arg_0]
0x140011905  mov     eax, r14d
0x140011908  add     rsp, 60h
0x14001190c  pop     r15
0x14001190e  pop     r14
0x140011910  pop     r13
0x140011912  pop     r12
0x140011914  pop     rdi
0x140011915  pop     rsi
0x140011916  pop     rbp
0x140011917  retn
```
