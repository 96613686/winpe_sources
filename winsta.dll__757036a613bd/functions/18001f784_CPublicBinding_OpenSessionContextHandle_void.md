# CPublicBinding::OpenSessionContextHandle(void *)

- ea: `0x18001f784`
- end: `0x18001f7d3`
- name: `?OpenSessionContextHandle@CPublicBinding@@AEAAJPEAX@Z`
- size: `79`
- prototype: `__int64 __fastcall(CPublicBinding *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005db0`

## callees

- `0x180007890`
- `0x180011368`
- `0x18001f784`

## string_xrefs

- `0x18001f7b9`: `RpcOpenSession threw an exception: 0x%x`

## pseudocode

```c
__int64 __fastcall CPublicBinding::OpenSessionContextHandle(CPublicBinding *this, void *a2)
{
  return (unsigned int)RpcOpenSession(a2, 0, (char *)this + 56);
}

```

## disassembly

```asm
0x18001f784  push    rbx
0x18001f786  sub     rsp, 30h
0x18001f78a  mov     rax, rdx
0x18001f78d  lea     r8, [rcx+38h]
0x18001f791  xor     edx, edx
0x18001f793  mov     rcx, rax
0x18001f796  call    RpcOpenSession
0x18001f79b  mov     ebx, eax
0x18001f79d  mov     [rsp+38h+var_18], eax
0x18001f7a1  jmp     short loc_18001F7CB
0x18001f7a3  mov     ebx, eax
0x18001f7a5  test    eax, eax
0x18001f7a7  jle     short loc_18001F7B2
0x18001f7a9  movzx   ebx, ax
0x18001f7ac  or      ebx, 80070000h
0x18001f7b2  mov     [rsp+38h+var_18], ebx
0x18001f7b6  mov     r8d, ebx
0x18001f7b9  lea     rdx, aRpcopensession_0; "RpcOpenSession threw an exception: 0x%x"
0x18001f7c0  mov     ecx, 8; int
0x18001f7c5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001f7ca  nop
0x18001f7cb  mov     eax, ebx
0x18001f7cd  add     rsp, 30h
0x18001f7d1  pop     rbx
0x18001f7d2  retn
0x18003082f  push    rbp
0x180030831  sub     rsp, 20h
0x180030835  mov     rbp, rdx
0x180030838  mov     rcx, [rcx]
0x18003083b  mov     ecx, [rcx]; ExceptionCode
0x18003083d  call    cs:__imp_I_RpcExceptionFilter
0x180030843  nop
0x180030844  add     rsp, 20h
0x180030848  pop     rbp
0x180030849  retn
```
