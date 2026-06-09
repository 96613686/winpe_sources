# DeviceObject::Create(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_SECURITY_DESCRIPTOR const *,bool,_DEVPROPERTY const *,ulong,void (*)(DeviceObject *,long,void *),void *,DeviceObjectCreationWaitMode,DeviceObject * *)

- ea: `0x1800132cc`
- end: `0x1800133e3`
- name: `?Create@DeviceObject@@SAJPEBG000000PEBU_SECURITY_DESCRIPTOR@@_NPEBU_DEVPROPERTY@@KP6AXPEAV1@JPEAX@Z5W4DeviceObjectCreationWaitMode@@PEAPEAV1@@Z`
- size: `279`
- prototype: `static int __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _SECURITY_DESCRIPTOR *, bool, const struct _DEVPROPERTY *, unsigned int, void (__high *)(struct DeviceObject *, int, void *), void *, enum DeviceObjectCreationWaitMode, struct DeviceObject **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800111f0`

## callees

- `0x180012234`
- `0x1800132cc`
- `0x1800133ec`
- `0x180013a64`
- `0x180013c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013370`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001338a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001338a`

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
0x1800132cc  mov     rax, rsp
0x1800132cf  mov     [rax+8], rbx
0x1800132d3  mov     [rax+20h], r9
0x1800132d7  push    rdi
0x1800132d8  sub     rsp, 80h
0x1800132df  lea     rcx, [rax+20h]
0x1800132e3  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x1800132eb  mov     rbx, rdx
0x1800132ee  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x1800132f3  mov     rdi, [rsp+88h+arg_70]
0x1800132fb  lea     rax, [rsp+88h+arg_18]
0x180013303  mov     [rsp+88h+var_18], rdi; struct DeviceObject **
0x180013308  mov     rdx, rbx; unsigned __int16 *
0x18001330b  mov     [rsp+88h+var_20], rax; void **
0x180013310  mov     eax, [rsp+88h+arg_50]
0x180013317  mov     [rsp+88h+var_38], eax; unsigned int
0x18001331b  mov     rax, [rsp+88h+arg_48]
0x180013323  mov     [rsp+88h+var_40], rax; struct _DEVPROPERTY *
0x180013328  mov     rax, [rsp+88h+arg_38]
0x180013330  mov     [rsp+88h+var_50], rax; struct _SECURITY_DESCRIPTOR *
0x180013335  mov     rax, [rsp+88h+arg_20]
0x18001333d  mov     [rsp+88h+lpsz], rax; lpsz
0x180013342  mov     [rsp+88h+arg_18], 0FFFFFFFFFFFFFFFFh
0x18001334e  call    ?CreateAsync@DeviceObject@@CAJPEBG000000PEBU_SECURITY_DESCRIPTOR@@_NPEBU_DEVPROPERTY@@KP6AXPEAV1@JPEAX@Z5PEAPEAXPEAPEAV1@@Z; DeviceObject::CreateAsync(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_SECURITY_DESCRIPTOR const *,bool,_DEVPROPERTY const *,ulong,void (*)(DeviceObject *,long,void *),void *,void * *,DeviceObject * *)
0x180013353  mov     ebx, eax
0x180013355  test    eax, eax
0x180013357  js      short loc_1800133AA
0x180013359  mov     rcx, [rsp+88h+arg_18]
0x180013361  xor     eax, eax
0x180013363  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180013367  cmovz   rcx, rax; hHandle
0x18001336b  or      ebx, 0FFFFFFFFh
0x18001336e  mov     edx, ebx; dwMilliseconds
0x180013370  call    cs:__imp_WaitForSingleObject
0x180013376  test    eax, eax
0x180013378  jnz     short loc_180013386
0x18001337a  mov     rcx, [rdi]; this
0x18001337d  call    ?IsValid@DeviceObject@@QEBAJXZ; DeviceObject::IsValid(void)
0x180013382  mov     ebx, eax
0x180013384  jmp     short loc_18001339F
0x180013386  cmp     eax, ebx
0x180013388  jnz     short loc_1800133A5
0x18001338a  call    cs:__imp_GetLastError
0x180013390  mov     ebx, eax
0x180013392  test    eax, eax
0x180013394  jle     short loc_18001339F
0x180013396  movzx   ebx, ax
0x180013399  or      ebx, 80070000h
0x18001339f  test    ebx, ebx
0x1800133a1  jns     short loc_1800133C3
0x1800133a3  jmp     short loc_1800133AA
0x1800133a5  mov     ebx, 8000FFFFh
0x1800133aa  test    rdi, rdi
0x1800133ad  jz      short loc_1800133C3
0x1800133af  mov     rcx, [rdi]; this
0x1800133b2  test    rcx, rcx
0x1800133b5  jz      short loc_1800133C3
0x1800133b7  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x1800133bc  mov     qword ptr [rdi], 0
0x1800133c3  lea     rcx, [rsp+88h+arg_18]
0x1800133cb  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x1800133d0  mov     eax, ebx
0x1800133d2  mov     rbx, [rsp+88h+arg_0]
0x1800133da  add     rsp, 80h
0x1800133e1  pop     rdi
0x1800133e2  retn
```
