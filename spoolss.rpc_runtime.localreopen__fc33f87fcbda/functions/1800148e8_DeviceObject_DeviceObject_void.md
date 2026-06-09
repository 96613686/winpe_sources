# DeviceObject::~DeviceObject(void)

- ea: `0x1800148e8`
- end: `0x18001493b`
- name: `??1DeviceObject@@UEAA@XZ`
- size: `83`
- prototype: `void __fastcall(DeviceObject *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800149e0`

## callees

- `0x180013acc`
- `0x1800148e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014909`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014909`

## pseudocode

```c
void __fastcall DeviceObject::~DeviceObject(DeviceObject *this)
{
  *(_QWORD *)this = &DeviceObject::`vftable';
  if ( *((int *)this + 24) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    *((_DWORD *)this + 24) = -2147467259;
  }
  NCoreLibrary::TString::vFree(this, *((void **)this + 5));
  *(_QWORD *)this = &NCoreLibrary::TReferenceCount::`vftable';
}

```

## disassembly

```asm
0x1800148e8  mov     [rsp+arg_0], rbx
0x1800148ed  push    rdi
0x1800148ee  sub     rsp, 20h
0x1800148f2  lea     rax, ??_7DeviceObject@@6B@; const DeviceObject::`vftable'
0x1800148f9  mov     rbx, rcx
0x1800148fc  mov     [rcx], rax
0x1800148ff  cmp     dword ptr [rcx+60h], 0
0x180014903  jl      short loc_18001491C
0x180014905  add     rcx, 30h ; '0'; lpCriticalSection
0x180014909  call    cs:__imp_DeleteCriticalSection
0x180014910  nop     dword ptr [rax+rax+00h]
0x180014915  mov     dword ptr [rbx+60h], 80004005h
0x18001491c  mov     rdx, [rbx+28h]; void *
0x180014920  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180014925  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x18001492c  mov     [rbx], rax
0x18001492f  mov     rbx, [rsp+28h+arg_0]
0x180014934  add     rsp, 20h
0x180014938  pop     rdi
0x180014939  retn
```
