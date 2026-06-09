# DeviceObject::Create(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_SECURITY_DESCRIPTOR const *,bool,_DEVPROPERTY const *,ulong,void (*)(DeviceObject *,long,void *),void *,DeviceObjectCreationWaitMode,DeviceObject * *)

- ea: `0x180014a50`
- end: `0x180014b74`
- name: `?Create@DeviceObject@@SAJPEBG000000PEBU_SECURITY_DESCRIPTOR@@_NPEBU_DEVPROPERTY@@KP6AXPEAV1@JPEAX@Z5W4DeviceObjectCreationWaitMode@@PEAPEAV1@@Z`
- size: `292`
- prototype: `static int __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _SECURITY_DESCRIPTOR *, bool, const struct _DEVPROPERTY *, unsigned int, void (__high *)(struct DeviceObject *, int, void *), void *, enum DeviceObjectCreationWaitMode, struct DeviceObject **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001285c`

## callees

- `0x1800139b0`
- `0x180014a50`
- `0x180014b7c`
- `0x1800151e4`
- `0x1800153c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014af4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b14`

## pseudocode

```c
__int64 __fastcall DeviceObject::Create(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        LPCOLESTR lpsz,
        __int64 a6,
        __int64 a7,
        struct _SECURITY_DESCRIPTOR *a8,
        __int64 a9,
        struct _DEVPROPERTY *a10,
        unsigned int a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        struct DeviceObject **a15)
{
  DeviceObject **v16; // rdi
  const unsigned __int16 *v17; // rcx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r9
  signed int IsValid; // ebx
  void *v21; // rcx
  DWORD v22; // eax
  signed int LastError; // eax
  const unsigned __int16 *v25; // [rsp+28h] [rbp-60h]
  const unsigned __int16 *v26; // [rsp+30h] [rbp-58h]
  bool v27; // [rsp+40h] [rbp-48h]
  void (*v28)(struct DeviceObject *, int, void *); // [rsp+58h] [rbp-30h]
  void *v29; // [rsp+60h] [rbp-28h]
  void *v30; // [rsp+A8h] [rbp+20h] BYREF

  v30 = (void *)-1LL;
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v30);
  v16 = a15;
  v30 = (void *)-1LL;
  IsValid = DeviceObject::CreateAsync(v17, a2, v18, v19, lpsz, v25, v26, a8, v27, a10, a11, v28, v29, &v30, a15);
  if ( IsValid >= 0 )
  {
    v21 = v30;
    if ( v30 == (void *)-1LL )
      v21 = 0;
    v22 = WaitForSingleObject(v21, 0xFFFFFFFF);
    if ( !v22 )
    {
      IsValid = DeviceObject::IsValid(*v16);
      goto LABEL_9;
    }
    if ( v22 == -1 )
    {
      LastError = GetLastError();
      IsValid = LastError;
      if ( LastError > 0 )
        IsValid = (unsigned __int16)LastError | 0x80070000;
LABEL_9:
      if ( IsValid >= 0 )
        goto LABEL_15;
      goto LABEL_12;
    }
    IsValid = -2147418113;
  }
LABEL_12:
  if ( v16 && *v16 )
  {
    NCoreLibrary::TReferenceCount::Release(*v16);
    *v16 = 0;
  }
LABEL_15:
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v30);
  return (unsigned int)IsValid;
}

```

## disassembly

```asm
0x180014a50  mov     rax, rsp
0x180014a53  mov     [rax+8], rbx
0x180014a57  mov     [rax+20h], r9
0x180014a5b  push    rdi
0x180014a5c  sub     rsp, 80h
0x180014a63  lea     rcx, [rax+20h]
0x180014a67  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x180014a6f  mov     rbx, rdx
0x180014a72  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x180014a77  mov     rdi, [rsp+88h+arg_70]
0x180014a7f  lea     rax, [rsp+88h+arg_18]
0x180014a87  mov     [rsp+88h+var_18], rdi; struct DeviceObject **
0x180014a8c  mov     rdx, rbx; unsigned __int16 *
0x180014a8f  mov     [rsp+88h+var_20], rax; void **
0x180014a94  mov     eax, [rsp+88h+arg_50]
0x180014a9b  mov     [rsp+88h+var_38], eax; unsigned int
0x180014a9f  mov     rax, [rsp+88h+arg_48]
0x180014aa7  mov     [rsp+88h+var_40], rax; struct _DEVPROPERTY *
0x180014aac  mov     rax, [rsp+88h+arg_38]
0x180014ab4  mov     [rsp+88h+var_50], rax; struct _SECURITY_DESCRIPTOR *
0x180014ab9  mov     rax, [rsp+88h+arg_20]
0x180014ac1  mov     [rsp+88h+lpsz], rax; lpsz
0x180014ac6  mov     [rsp+88h+arg_18], 0FFFFFFFFFFFFFFFFh
0x180014ad2  call    ?CreateAsync@DeviceObject@@CAJPEBG000000PEBU_SECURITY_DESCRIPTOR@@_NPEBU_DEVPROPERTY@@KP6AXPEAV1@JPEAX@Z5PEAPEAXPEAPEAV1@@Z; DeviceObject::CreateAsync(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_SECURITY_DESCRIPTOR const *,bool,_DEVPROPERTY const *,ulong,void (*)(DeviceObject *,long,void *),void *,void * *,DeviceObject * *)
0x180014ad7  mov     ebx, eax
0x180014ad9  test    eax, eax
0x180014adb  js      short loc_180014B3A
0x180014add  mov     rcx, [rsp+88h+arg_18]
0x180014ae5  xor     eax, eax
0x180014ae7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180014aeb  cmovz   rcx, rax; hHandle
0x180014aef  or      ebx, 0FFFFFFFFh
0x180014af2  mov     edx, ebx; dwMilliseconds
0x180014af4  call    cs:__imp_WaitForSingleObject
0x180014afb  nop     dword ptr [rax+rax+00h]
0x180014b00  test    eax, eax
0x180014b02  jnz     short loc_180014B10
0x180014b04  mov     rcx, [rdi]; this
0x180014b07  call    ?IsValid@DeviceObject@@QEBAJXZ; DeviceObject::IsValid(void)
0x180014b0c  mov     ebx, eax
0x180014b0e  jmp     short loc_180014B2F
0x180014b10  cmp     eax, ebx
0x180014b12  jnz     short loc_180014B35
0x180014b14  call    cs:__imp_GetLastError
0x180014b1b  nop     dword ptr [rax+rax+00h]
0x180014b20  mov     ebx, eax
0x180014b22  test    eax, eax
0x180014b24  jle     short loc_180014B2F
0x180014b26  movzx   ebx, ax
0x180014b29  or      ebx, 80070000h
0x180014b2f  test    ebx, ebx
0x180014b31  jns     short loc_180014B53
0x180014b33  jmp     short loc_180014B3A
0x180014b35  mov     ebx, 8000FFFFh
0x180014b3a  test    rdi, rdi
0x180014b3d  jz      short loc_180014B53
0x180014b3f  mov     rcx, [rdi]; this
0x180014b42  test    rcx, rcx
0x180014b45  jz      short loc_180014B53
0x180014b47  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x180014b4c  mov     qword ptr [rdi], 0
0x180014b53  lea     rcx, [rsp+88h+arg_18]
0x180014b5b  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x180014b60  mov     eax, ebx
0x180014b62  mov     rbx, [rsp+88h+arg_0]
0x180014b6a  add     rsp, 80h
0x180014b71  pop     rdi
0x180014b72  retn
```
