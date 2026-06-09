# DeviceObject::~DeviceObject(void)

- ea: `0x180013180`
- end: `0x1800131cc`
- name: `??1DeviceObject@@UEAA@XZ`
- size: `76`
- prototype: `void __fastcall(DeviceObject *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013260`

## callees

- `0x180012344`
- `0x180013180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800131a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800131a1`

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
0x180013180  mov     [rsp+arg_0], rbx
0x180013185  push    rdi
0x180013186  sub     rsp, 20h
0x18001318a  lea     rax, ??_7DeviceObject@@6B@; const DeviceObject::`vftable'
0x180013191  mov     rbx, rcx
0x180013194  mov     [rcx], rax
0x180013197  cmp     dword ptr [rcx+60h], 0
0x18001319b  jl      short loc_1800131AE
0x18001319d  add     rcx, 30h ; '0'; lpCriticalSection
0x1800131a1  call    cs:__imp_DeleteCriticalSection
0x1800131a7  mov     dword ptr [rbx+60h], 80004005h
0x1800131ae  mov     rdx, [rbx+28h]; void *
0x1800131b2  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x1800131b7  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x1800131be  mov     [rbx], rax
0x1800131c1  mov     rbx, [rsp+28h+arg_0]
0x1800131c6  add     rsp, 20h
0x1800131ca  pop     rdi
0x1800131cb  retn
```
