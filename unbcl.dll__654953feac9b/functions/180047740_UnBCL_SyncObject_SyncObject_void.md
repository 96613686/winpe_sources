# UnBCL::SyncObject::~SyncObject(void)

- ea: `0x180047740`
- end: `0x1800477c9`
- name: `??1SyncObject@UnBCL@@UEAA@XZ`
- size: `137`
- prototype: `void __fastcall(UnBCL::SyncObject *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800479b0`

## callees

- `0x180047740`
- `0x18006f010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180047773`
- `KERNEL32!CloseHandle` at `0x18004778a`
- `KERNEL32!CloseHandle` at `0x180047773`
- `KERNEL32!CloseHandle` at `0x18004778a`
- `KERNEL32!DeleteCriticalSection` at `0x180047764`
- `KERNEL32!DeleteCriticalSection` at `0x180047764`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UnBCL::SyncObject::~SyncObject(UnBCL::SyncObject *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &UnBCL::SyncObject::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
  if ( v4 )
  {
    (**v4)(v4, 1);
    *((_QWORD *)this + 4) = 0;
  }
  *(_QWORD *)this = &UnBCL::Object::`vftable';
}

```

## disassembly

```asm
0x180047740  mov     [rsp+arg_0], rcx
0x180047745  push    rbx
0x180047746  sub     rsp, 30h
0x18004774a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180047753  mov     rbx, rcx
0x180047756  lea     rax, ??_7SyncObject@UnBCL@@6B@; const UnBCL::SyncObject::`vftable'
0x18004775d  mov     [rcx], rax
0x180047760  add     rcx, 30h ; '0'; lpCriticalSection
0x180047764  call    cs:__imp_DeleteCriticalSection
0x18004776a  mov     rcx, [rbx+10h]; hObject
0x18004776e  test    rcx, rcx
0x180047771  jz      short loc_180047781
0x180047773  call    cs:__imp_CloseHandle
0x180047779  mov     qword ptr [rbx+10h], 0
0x180047781  mov     rcx, [rbx+18h]; hObject
0x180047785  test    rcx, rcx
0x180047788  jz      short loc_180047798
0x18004778a  call    cs:__imp_CloseHandle
0x180047790  mov     qword ptr [rbx+18h], 0
0x180047798  mov     rcx, [rbx+20h]
0x18004779c  test    rcx, rcx
0x18004779f  jz      short loc_1800477B9
0x1800477a1  mov     rax, [rcx]
0x1800477a4  mov     edx, 1
0x1800477a9  mov     rax, [rax]
0x1800477ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477b1  mov     qword ptr [rbx+20h], 0
0x1800477b9  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x1800477c0  mov     [rbx], rax
0x1800477c3  add     rsp, 30h
0x1800477c7  pop     rbx
0x1800477c8  retn
```
