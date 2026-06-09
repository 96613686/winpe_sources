# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000cf4c`
- end: `0x18000cfb7`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cfc0`

## callees

- `0x18000cf08`
- `0x18000cf4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf62`

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
0x18000cf4c  mov     [rsp+arg_0], rbx
0x18000cf51  push    rdi; int
0x18000cf52  sub     rsp, 20h
0x18000cf56  cmp     dword ptr [rcx+18h], 0
0x18000cf5a  mov     rdi, rcx
0x18000cf5d  jz      short loc_18000CFAC
0x18000cf5f  mov     ebx, [rcx+18h]
0x18000cf62  call    cs:__imp_GetCurrentThreadId
0x18000cf68  cmp     ebx, eax
0x18000cf6a  jz      short loc_18000CF7C
0x18000cf6c  mov     rcx, [rsp+28h]; this
0x18000cf71  mov     r9d, 8007029Ch; char *
0x18000cf77  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000cf7c  mov     rcx, [rdi]
0x18000cf7f  mov     dword ptr [rdi+18h], 0
0x18000cf86  jmp     short loc_18000CF94
0x18000cf88  cmp     rax, rdi
0x18000cf8b  jz      short loc_18000CF9E
0x18000cf8d  lea     rcx, [rax+10h]
0x18000cf91  mov     [rdi], rcx
0x18000cf94  mov     rax, [rcx]
0x18000cf97  test    rax, rax
0x18000cf9a  jnz     short loc_18000CF88
0x18000cf9c  jmp     short loc_18000CFA5
0x18000cf9e  mov     rax, [rdi+10h]
0x18000cfa2  mov     [rcx], rax
0x18000cfa5  mov     qword ptr [rdi], 0
0x18000cfac  mov     rbx, [rsp+28h+arg_0]
0x18000cfb1  add     rsp, 20h
0x18000cfb5  pop     rdi
0x18000cfb6  retn
```
