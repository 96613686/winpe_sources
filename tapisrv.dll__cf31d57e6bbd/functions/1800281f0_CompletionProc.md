# CompletionProc

- ea: `0x1800281f0`
- end: `0x1800282ed`
- name: `CompletionProc`
- size: `253`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005378`
- `0x180028300`
- `0x18002c4d0`

## callees

- `0x180001600`
- `0x1800281f0`
- `0x18002c8d4`
- `0x18002f778`
- `0x18003dc84`
- `0x180040010`

## string_xrefs

- `0x180028221`: `CompletionProc: enter, dwReqID=x%x, lResult=x%x`

## pseudocode

```c
void __fastcall CompletionProc(__int64 a1, unsigned int a2)
{
  char v4; // al
  bool v5; // cf
  void (__fastcall *v6)(__int64, unsigned int *, LPVOID *); // rax
  unsigned int *v7; // rdx
  LPVOID lpMem[2]; // [rsp+20h] [rbp-19h] BYREF
  unsigned int v9[20]; // [rsp+30h] [rbp-9h] BYREF

  TRACELogPrint(524290, "CompletionProc: enter, dwReqID=x%x, lResult=x%x", *(_DWORD *)(a1 + 72), a2);
  v9[1] = *(_DWORD *)(a1 + 60);
  v9[2] = *(_DWORD *)(a1 + 68);
  v4 = *(_DWORD *)(a1 + 56) & 1;
  *(_DWORD *)a1 = 1280724553;
  v5 = v4 != 0;
  v9[0] = 40;
  v9[5] = *(_DWORD *)(a1 + 64);
  v9[6] = *(_DWORD *)(a1 + 76);
  v6 = *(void (__fastcall **)(__int64, unsigned int *, LPVOID *))(a1 + 48);
  v9[3] = 0;
  v9[4] = v5 ? 12 : 17;
  v9[7] = a2;
  v9[8] = 0;
  if ( v6 )
  {
    lpMem[0] = 0;
    v6(a1, v9, lpMem);
    v7 = v9;
    if ( lpMem[0] )
      v7 = (unsigned int *)lpMem[0];
    WriteEventBuffer(*(_QWORD *)(a1 + 32), v7);
    if ( lpMem[0] )
      ServerFree(lpMem[0]);
  }
  else
  {
    WriteEventBuffer(*(_QWORD *)(a1 + 32), v9);
  }
}

```

## disassembly

```asm
0x1800281f0  mov     [rsp-8+arg_10], rbx
0x1800281f5  mov     [rsp-8+arg_18], rdi
0x1800281fa  push    rbp
0x1800281fb  lea     rbp, [rsp-57h]
0x180028200  sub     rsp, 90h
0x180028207  mov     rax, cs:__security_cookie
0x18002820e  xor     rax, rsp
0x180028211  mov     [rbp+57h+var_10], rax
0x180028215  mov     r8d, [rcx+48h]
0x180028219  mov     ebx, edx
0x18002821b  mov     rdi, rcx
0x18002821e  mov     r9d, edx
0x180028221  lea     rdx, aCompletionproc; "CompletionProc: enter, dwReqID=x%x, lRe"...
0x180028228  mov     ecx, 80002h
0x18002822d  call    TRACELogPrint
0x180028232  mov     eax, [rdi+3Ch]
0x180028235  lea     rdx, [rbp+57h+var_60]
0x180028239  mov     [rbp+57h+var_5C], eax
0x18002823c  mov     eax, [rdi+44h]
0x18002823f  mov     [rbp+57h+var_58], eax
0x180028242  mov     eax, [rdi+38h]
0x180028245  and     al, 1
0x180028247  mov     dword ptr [rdi], 4C564E49h
0x18002824d  neg     al
0x18002824f  mov     [rbp+57h+var_60], 28h ; '('
0x180028256  mov     eax, [rdi+40h]
0x180028259  sbb     ecx, ecx
0x18002825b  mov     [rbp+57h+var_4C], eax
0x18002825e  mov     eax, [rdi+4Ch]
0x180028261  and     ecx, 0FFFFFFFBh
0x180028264  add     ecx, 11h
0x180028267  mov     [rbp+57h+var_48], eax
0x18002826a  mov     rax, [rdi+30h]
0x18002826e  mov     [rbp+57h+var_54], 0
0x180028275  mov     [rbp+57h+var_50], ecx
0x180028278  mov     [rbp+57h+var_44], ebx
0x18002827b  mov     [rbp+57h+var_40], 0
0x180028282  test    rax, rax
0x180028285  jz      short loc_1800282C3
0x180028287  lea     r8, [rbp+57h+lpMem]
0x18002828b  mov     [rbp+57h+lpMem], 0
0x180028293  mov     rcx, rdi
0x180028296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002829b  mov     rax, [rbp+57h+lpMem]
0x18002829f  lea     rdx, [rbp+57h+var_60]
0x1800282a3  mov     rcx, [rdi+20h]
0x1800282a7  test    rax, rax
0x1800282aa  cmovnz  rdx, rax
0x1800282ae  call    WriteEventBuffer
0x1800282b3  mov     rcx, [rbp+57h+lpMem]; lpMem
0x1800282b7  test    rcx, rcx
0x1800282ba  jz      short loc_1800282CC
0x1800282bc  call    ServerFree
0x1800282c1  jmp     short loc_1800282CC
0x1800282c3  mov     rcx, [rdi+20h]
0x1800282c7  call    WriteEventBuffer
0x1800282cc  mov     rcx, [rbp+57h+var_10]
0x1800282d0  xor     rcx, rsp; StackCookie
0x1800282d3  call    __security_check_cookie
0x1800282d8  lea     r11, [rsp+90h+var_s0]
0x1800282e0  mov     rbx, [r11+20h]
0x1800282e4  mov     rdi, [r11+28h]
0x1800282e8  mov     rsp, r11
0x1800282eb  pop     rbp
0x1800282ec  retn
```
