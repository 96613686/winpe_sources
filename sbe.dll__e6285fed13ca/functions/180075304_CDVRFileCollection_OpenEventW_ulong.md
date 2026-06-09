# CDVRFileCollection::OpenEventW(ulong)

- ea: `0x180075304`
- end: `0x180075401`
- name: `?OpenEventW@CDVRFileCollection@@IEAAJK@Z`
- size: `253`
- prototype: `__int64 __fastcall(CDVRFileCollection *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180076bec`

## callees

- `0x180001c00`
- `0x18000262c`
- `0x180075304`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180075369`
- `KERNEL32!CloseHandle` at `0x180075369`
- `KERNEL32!GetLastError` at `0x1800753aa`
- `KERNEL32!GetLastError` at `0x1800753aa`
- `KERNEL32!OpenEventW` at `0x180075389`
- `KERNEL32!OpenEventW` at `0x180075389`

## pseudocode

```c
__int64 __fastcall CDVRFileCollection::OpenEventW(CDVRFileCollection *this, unsigned int a2)
{
  __int64 v3; // rbx
  void *v4; // rcx
  __int64 v5; // rax
  signed int LastError; // eax
  unsigned int v7; // edx
  int v9; // [rsp+20h] [rbp-78h]
  wchar_t Buffer[40]; // [rsp+30h] [rbp-68h] BYREF

  v3 = 5LL * a2;
  v9 = *(_DWORD *)(*((_QWORD *)this + 4) + 40LL * a2 + 624);
  swprintf_s(Buffer, 0x28u, L"%s%u", L"Global\\_MS_TSDVR_EVENT_", v9);
  v4 = *(void **)(*((_QWORD *)this + 4) + 8 * v3 + 616);
  if ( v4 )
  {
    CloseHandle(v4);
    *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v3 + 616) = 0;
  }
  *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v3 + 616) = OpenEventW(2u, 0, Buffer);
  v5 = *((_QWORD *)this + 4);
  if ( *(_QWORD *)(v5 + 8 * v3 + 616) )
  {
    v7 = 0;
    *(_DWORD *)(v5 + 8 * v3 + 648) = *(_DWORD *)(v5 + 8 * v3 + 644);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    *(_WORD *)(*((_QWORD *)this + 4) + 8 * v3 + 654) |= 8u;
  }
  return v7;
}

```

## disassembly

```asm
0x180075304  mov     [rsp+arg_10], rbx
0x180075309  push    rdi
0x18007530a  sub     rsp, 90h
0x180075311  mov     rax, cs:__security_cookie
0x180075318  xor     rax, rsp
0x18007531b  mov     [rsp+98h+var_18], rax
0x180075323  mov     eax, edx
0x180075325  lea     r9, aGlobalMsTsdvrE; "Global\\_MS_TSDVR_EVENT_"
0x18007532c  mov     rdi, rcx
0x18007532f  lea     r8, aSU; "%s%u"
0x180075336  lea     rbx, [rax+rax*4]
0x18007533a  mov     rax, [rcx+20h]
0x18007533e  lea     rcx, [rsp+98h+Buffer]; Buffer
0x180075343  mov     edx, [rax+rbx*8+270h]
0x18007534a  mov     [rsp+98h+var_78], edx
0x18007534e  mov     edx, 28h ; '('; BufferCount
0x180075353  call    swprintf_s
0x180075358  mov     rax, [rdi+20h]
0x18007535c  mov     rcx, [rax+rbx*8+268h]; hObject
0x180075364  test    rcx, rcx
0x180075367  jz      short loc_18007537F
0x180075369  call    cs:__imp_CloseHandle
0x18007536f  mov     rax, [rdi+20h]
0x180075373  mov     qword ptr [rax+rbx*8+268h], 0
0x18007537f  xor     edx, edx; bInheritHandle
0x180075381  lea     r8, [rsp+98h+Buffer]; lpName
0x180075386  lea     ecx, [rdx+2]; dwDesiredAccess
0x180075389  call    cs:__imp_OpenEventW
0x18007538f  mov     rcx, [rdi+20h]
0x180075393  mov     [rcx+rbx*8+268h], rax
0x18007539b  mov     rax, [rdi+20h]
0x18007539f  cmp     qword ptr [rax+rbx*8+268h], 0
0x1800753a8  jnz     short loc_1800753CE
0x1800753aa  call    cs:__imp_GetLastError
0x1800753b0  mov     edx, eax
0x1800753b2  test    eax, eax
0x1800753b4  jle     short loc_1800753BF
0x1800753b6  movzx   edx, ax
0x1800753b9  or      edx, 80070000h
0x1800753bf  mov     rax, [rdi+20h]
0x1800753c3  or      word ptr [rax+rbx*8+28Eh], 8
0x1800753cc  jmp     short loc_1800753DE
0x1800753ce  mov     ecx, [rax+rbx*8+284h]
0x1800753d5  xor     edx, edx
0x1800753d7  mov     [rax+rbx*8+288h], ecx
0x1800753de  mov     eax, edx
0x1800753e0  mov     rcx, [rsp+98h+var_18]
0x1800753e8  xor     rcx, rsp; StackCookie
0x1800753eb  call    __security_check_cookie
0x1800753f0  mov     rbx, [rsp+98h+arg_10]
0x1800753f8  add     rsp, 90h
0x1800753ff  pop     rdi
0x180075400  retn
```
