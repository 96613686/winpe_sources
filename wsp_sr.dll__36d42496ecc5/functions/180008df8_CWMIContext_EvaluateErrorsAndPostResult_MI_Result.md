# CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)

- ea: `0x180008df8`
- end: `0x180008e8c`
- name: `?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z`
- size: `148`
- prototype: `void __fastcall(CWMIContext *this, MI_Uint32)`
- caller_count: `22`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008fb0`
- `0x18000934c`
- `0x180009844`
- `0x180009a88`
- `0x180009c48`
- `0x18000bec0`
- `0x18000c2b4`
- `0x18000c8a0`
- `0x18000e5d4`
- `0x18000e874`
- `0x18000ebd4`
- `0x18000ffc4`
- `0x1800100d0`
- `0x18001039c`
- `0x18001056c`
- `0x1800107f8`
- `0x180010a68`
- `0x180010c38`
- `0x180011d9c`
- `0x1800152ec`
- `0x1800160c8`
- `0x1800161cc`

## callees

- `0x180008df8`
- `0x180008e94`
- `0x18002d010`

## pseudocode

```c
void __fastcall CWMIContext::EvaluateErrorsAndPostResult(CWMIContext *this, MI_Uint32 a2)
{
  const MI_Char *v2; // r9
  MI_Context *v3; // rcx
  const MI_Char *v4; // r8

  v2 = 0;
  if ( *((_BYTE *)this + 8) )
  {
    a2 = *((_DWORD *)this + 17);
    if ( a2 )
    {
      if ( *((_BYTE *)this + 9) )
      {
        v2 = (const MI_Char *)((char *)this + 16);
        if ( *((_QWORD *)this + 5) > 7u )
          v2 = *(const MI_Char **)v2;
      }
      v4 = L"WIN32";
    }
    else
    {
      a2 = *((_DWORD *)this + 16);
      if ( !a2 )
      {
        v3 = (MI_Context *)*((_QWORD *)this + 7);
        a2 = 1;
        goto LABEL_18;
      }
      if ( *((_BYTE *)this + 9) )
      {
        v2 = (const MI_Char *)((char *)this + 16);
        if ( *((_QWORD *)this + 5) > 7u )
          v2 = *(const MI_Char **)v2;
      }
      v4 = L"HRESULT";
    }
    v3 = (MI_Context *)*((_QWORD *)this + 7);
LABEL_19:
    MI_Context_PostError(v3, a2, v4, v2);
    return;
  }
  v3 = (MI_Context *)*((_QWORD *)this + 7);
  if ( a2 )
  {
LABEL_18:
    v4 = L"MI";
    goto LABEL_19;
  }
  if ( v3 )
  {
    if ( v3->ft )
      ((void (*)(void))v3->ft->PostResult)();
  }
}

```

## disassembly

```asm
0x180008df8  sub     rsp, 28h
0x180008dfc  xor     r9d, r9d; errorMessage
0x180008dff  cmp     [rcx+8], r9b
0x180008e03  jnz     short loc_180008E26
0x180008e05  mov     rcx, [rcx+38h]
0x180008e09  test    edx, edx
0x180008e0b  jnz     short loc_180008E7B
0x180008e0d  test    rcx, rcx
0x180008e10  jz      short loc_180008E87
0x180008e12  mov     rax, [rcx]
0x180008e15  test    rax, rax
0x180008e18  jz      short loc_180008E87
0x180008e1a  mov     rax, [rax]
0x180008e1d  add     rsp, 28h
0x180008e21  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180008e26  mov     edx, [rcx+44h]
0x180008e29  test    edx, edx
0x180008e2b  jz      short loc_180008E4E
0x180008e2d  cmp     [rcx+9], r9b
0x180008e31  jz      short loc_180008E41
0x180008e33  lea     r9, [rcx+10h]
0x180008e37  cmp     qword ptr [r9+18h], 7
0x180008e3c  jbe     short loc_180008E41
0x180008e3e  mov     r9, [r9]
0x180008e41  lea     r8, aWin32_0; "WIN32"
0x180008e48  mov     rcx, [rcx+38h]
0x180008e4c  jmp     short loc_180008E82
0x180008e4e  mov     edx, [rcx+40h]
0x180008e51  test    edx, edx
0x180008e53  jz      short loc_180008E72
0x180008e55  cmp     [rcx+9], r9b
0x180008e59  jz      short loc_180008E69
0x180008e5b  lea     r9, [rcx+10h]
0x180008e5f  cmp     qword ptr [r9+18h], 7
0x180008e64  jbe     short loc_180008E69
0x180008e66  mov     r9, [r9]
0x180008e69  lea     r8, aHresult_0; "HRESULT"
0x180008e70  jmp     short loc_180008E48
0x180008e72  mov     rcx, [rcx+38h]; context
0x180008e76  mov     edx, 1; resultCode
0x180008e7b  lea     r8, resultType; "MI"
0x180008e82  call    MI_Context_PostError
0x180008e87  add     rsp, 28h
0x180008e8b  retn
```
