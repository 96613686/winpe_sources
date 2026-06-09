# BASE_HTTP2_CONNECTION::From_BASE_CONNECTION(BASE_CONNECTION *)

- ea: `0x18000ab40`
- end: `0x18000ab91`
- name: `?From_BASE_CONNECTION@BASE_HTTP2_CONNECTION@@SAPEAV1@PEAVBASE_CONNECTION@@@Z`
- size: `81`
- prototype: `struct BASE_HTTP2_CONNECTION *__fastcall(struct BASE_CONNECTION *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180003da0`
- `0x1800048d8`
- `0x180004fc8`
- `0x18000a940`
- `0x18000b4c0`
- `0x18000b6e0`
- `0x18000dfe8`
- `0x180017370`

## callees

- `0x18000ab40`
- `0x18001b930`

## pseudocode

```c
struct BASE_HTTP2_CONNECTION *__fastcall BASE_HTTP2_CONNECTION::From_BASE_CONNECTION(struct BASE_CONNECTION *a1)
{
  if ( *((_DWORD *)a1 + 3) == 6 || *((_DWORD *)a1 + 3) == 10 || *((_DWORD *)a1 + 3) == 11 || *((_DWORD *)a1 + 3) == 12 )
    return (struct BASE_CONNECTION *)((char *)a1 + 424);
  if ( (unsigned int)(*((_DWORD *)a1 + 3) - 13) >= 2 )
  {
    RpcpReportFatalError(0x15u, 0);
    __debugbreak();
  }
  return (struct BASE_HTTP2_CONNECTION *)(((unsigned __int64)a1 + 176) & -(__int64)(a1 != 0));
}

```

## disassembly

```asm
0x18000ab40  sub     rsp, 28h
0x18000ab44  mov     edx, [rcx+0Ch]
0x18000ab47  sub     edx, 6
0x18000ab4a  jz      short loc_18000AB82
0x18000ab4c  sub     edx, 4
0x18000ab4f  jz      short loc_18000AB82
0x18000ab51  sub     edx, 1
0x18000ab54  jz      short loc_18000AB82
0x18000ab56  sub     edx, 1
0x18000ab59  jz      short loc_18000AB82
0x18000ab5b  sub     edx, 1
0x18000ab5e  jz      short loc_18000AB70
0x18000ab60  cmp     edx, 1
0x18000ab63  jz      short loc_18000AB70
0x18000ab65  xor     edx, edx
0x18000ab67  lea     ecx, [rdx+15h]
0x18000ab6a  call    RpcpReportFatalError
0x18000ab6f  int     3; Trap to Debugger
0x18000ab70  lea     rax, [rcx+0B0h]
0x18000ab77  neg     rcx
0x18000ab7a  sbb     rcx, rcx
0x18000ab7d  and     rcx, rax
0x18000ab80  jmp     short loc_18000AB89
0x18000ab82  add     rcx, 1A8h
0x18000ab89  mov     rax, rcx
0x18000ab8c  add     rsp, 28h
0x18000ab90  retn
```
