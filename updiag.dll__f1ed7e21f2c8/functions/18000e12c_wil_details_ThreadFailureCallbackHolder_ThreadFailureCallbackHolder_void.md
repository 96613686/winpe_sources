# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000e12c`
- end: `0x18000e197`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `107`
- prototype: `void(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c578`
- `0x18000c9fc`
- `0x18000cb98`
- `0x18000cd28`
- `0x18000ceb8`
- `0x18000d048`
- `0x18000d1d8`
- `0x18000d368`
- `0x18000d4f8`
- `0x18000d6a0`
- `0x180017e08`

## callees

- `0x18000e0e8`
- `0x18000e12c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e142`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e142`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  void *v3; // rdx
  unsigned int v4; // r8d
  wil::details::ThreadFailureCallbackHolder **v5; // rcx
  wil::details::ThreadFailureCallbackHolder *v6; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) )
  {
    v2 = *((_DWORD *)this + 6);
    if ( v2 != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v3, v4, (const char *)0x8007029CLL, v7);
    v5 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    *((_DWORD *)this + 6) = 0;
    while ( 1 )
    {
      v6 = *v5;
      if ( !*v5 )
        break;
      if ( v6 == this )
      {
        *v5 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
        break;
      }
      v5 = (wil::details::ThreadFailureCallbackHolder **)((char *)v6 + 16);
      *(_QWORD *)this = (char *)v6 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000e12c  mov     [rsp+arg_0], rbx
0x18000e131  push    rdi; int
0x18000e132  sub     rsp, 20h
0x18000e136  cmp     dword ptr [rcx+18h], 0
0x18000e13a  mov     rdi, rcx
0x18000e13d  jz      short loc_18000E18C
0x18000e13f  mov     ebx, [rcx+18h]
0x18000e142  call    cs:__imp_GetCurrentThreadId
0x18000e148  cmp     ebx, eax
0x18000e14a  jz      short loc_18000E15C
0x18000e14c  mov     rcx, [rsp+28h]; this
0x18000e151  mov     r9d, 8007029Ch; char *
0x18000e157  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000e15c  mov     rcx, [rdi]
0x18000e15f  mov     dword ptr [rdi+18h], 0
0x18000e166  jmp     short loc_18000E174
0x18000e168  cmp     rax, rdi
0x18000e16b  jz      short loc_18000E17E
0x18000e16d  lea     rcx, [rax+10h]
0x18000e171  mov     [rdi], rcx
0x18000e174  mov     rax, [rcx]
0x18000e177  test    rax, rax
0x18000e17a  jnz     short loc_18000E168
0x18000e17c  jmp     short loc_18000E185
0x18000e17e  mov     rax, [rdi+10h]
0x18000e182  mov     [rcx], rax
0x18000e185  mov     qword ptr [rdi], 0
0x18000e18c  mov     rbx, [rsp+28h+arg_0]
0x18000e191  add     rsp, 20h
0x18000e195  pop     rdi
0x18000e196  retn
```
