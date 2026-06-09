# CShellNotification::~CShellNotification(void)

- ea: `0x180013f10`
- end: `0x180013f69`
- name: `??1CShellNotification@@QEAA@XZ`
- size: `89`
- prototype: `void __fastcall(CShellNotification *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000f6cc`

## callees

- `0x180003fc4`
- `0x180013f10`
- `0x18001439c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180013f62`
- `KERNEL32!FreeLibrary` at `0x180013f33`
- `KERNEL32!FreeLibrary` at `0x180013f33`

## pseudocode

```c
void __fastcall CShellNotification::~CShellNotification(CShellNotification *this)
{
  _QWORD *v2; // rdi
  HMODULE v3; // rcx

  v2 = (_QWORD *)((char *)this + 1072);
  v3 = (HMODULE)*((_QWORD *)this + 134);
  *v2 = 0;
  if ( v3 )
    FreeLibrary(v3);
  *((_QWORD *)this + 135) = 0;
  CShellNotification::Delete(this);
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x180013f10  mov     [rsp+arg_0], rbx
0x180013f15  push    rdi
0x180013f16  sub     rsp, 20h
0x180013f1a  mov     rbx, rcx
0x180013f1d  lea     rdi, [rcx+430h]
0x180013f24  mov     rcx, [rdi]; hLibModule
0x180013f27  mov     qword ptr [rdi], 0
0x180013f2e  test    rcx, rcx
0x180013f31  jz      short loc_180013F39
0x180013f33  call    cs:__imp_FreeLibrary
0x180013f39  mov     qword ptr [rbx+438h], 0
0x180013f44  mov     rcx, rbx; this
0x180013f47  call    ?Delete@CShellNotification@@QEAAJXZ; CShellNotification::Delete(void)
0x180013f4c  mov     rcx, rdi
0x180013f4f  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x180013f54  lea     rcx, [rbx+18h]
0x180013f58  mov     rbx, [rsp+28h+arg_0]
0x180013f5d  add     rsp, 20h
0x180013f61  pop     rdi
0x180013f62  jmp     cs:__imp_DeleteCriticalSection
```
