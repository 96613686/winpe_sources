# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800019f0`
- end: `0x180001a55`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `101`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800019c0`

## callees

- `0x1800019f0`
- `0x180004370`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001a3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001a3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this)
{
  struct ATL::_ATL_MODULE70 *v2; // rcx
  __int64 v3; // rcx

  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v2 = (ATL::CAtlModule *)((char *)this + 8);
      if ( !this )
        v2 = 0;
      ATL::AtlCallTermFunc(v2);
      *((_QWORD *)this + 2) = 0;
    }
    v3 = *((_QWORD *)this + 8);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x1800019f0  mov     [rsp+arg_0], rbx
0x1800019f5  push    rdi
0x1800019f6  sub     rsp, 20h
0x1800019fa  mov     rbx, rcx
0x1800019fd  cmp     dword ptr [rcx+8], 0
0x180001a01  jz      short loc_180001A4A
0x180001a03  cmp     qword ptr [rcx+10h], 0
0x180001a08  jz      short loc_180001A24
0x180001a0a  add     rcx, 8
0x180001a0e  xor     eax, eax
0x180001a10  test    rbx, rbx
0x180001a13  cmovz   rcx, rax; struct ATL::_ATL_MODULE70 *
0x180001a17  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x180001a1c  mov     qword ptr [rbx+10h], 0
0x180001a24  mov     rcx, [rbx+40h]
0x180001a28  test    rcx, rcx
0x180001a2b  jz      short loc_180001A39
0x180001a2d  mov     rax, [rcx]
0x180001a30  mov     rax, [rax+10h]
0x180001a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a39  lea     rcx, [rbx+18h]; lpCriticalSection
0x180001a3d  call    cs:__imp_DeleteCriticalSection
0x180001a43  mov     dword ptr [rbx+8], 0
0x180001a4a  mov     rbx, [rsp+28h+arg_0]
0x180001a4f  add     rsp, 20h
0x180001a53  pop     rdi
0x180001a54  retn
```
