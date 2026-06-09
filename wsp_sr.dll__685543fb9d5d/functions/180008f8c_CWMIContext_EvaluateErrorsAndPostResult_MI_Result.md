# CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)

- ea: `0x180008f8c`
- end: `0x180009021`
- name: `?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z`
- size: `149`
- prototype: `void __fastcall(CWMIContext *__hidden this, enum _MI_Result)`
- caller_count: `22`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000916c`
- `0x18000950c`
- `0x180009994`
- `0x180009bd8`
- `0x180009d9c`
- `0x18000bf54`
- `0x18000c348`
- `0x18000c8c8`
- `0x18000e5a8`
- `0x18000e848`
- `0x18000eba8`
- `0x18000ff9c`
- `0x1800100a8`
- `0x180010354`
- `0x1800104f0`
- `0x18001075c`
- `0x180010998`
- `0x180010b34`
- `0x180011c64`
- `0x1800151a0`
- `0x180015f7c`
- `0x180016084`

## callees

- `0x180008f8c`
- `0x18000904c`
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
0x180008f8c  sub     rsp, 28h
0x180008f90  xor     r9d, r9d; errorMessage
0x180008f93  cmp     [rcx+8], r9b
0x180008f97  jnz     short loc_180008FBA
0x180008f99  mov     rcx, [rcx+38h]
0x180008f9d  test    edx, edx
0x180008f9f  jnz     short loc_18000900F
0x180008fa1  test    rcx, rcx
0x180008fa4  jz      short loc_18000901B
0x180008fa6  mov     rax, [rcx]
0x180008fa9  test    rax, rax
0x180008fac  jz      short loc_18000901B
0x180008fae  mov     rax, [rax]
0x180008fb1  add     rsp, 28h
0x180008fb5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180008fba  mov     edx, [rcx+44h]
0x180008fbd  test    edx, edx
0x180008fbf  jz      short loc_180008FE2
0x180008fc1  cmp     [rcx+9], r9b
0x180008fc5  jz      short loc_180008FD5
0x180008fc7  lea     r9, [rcx+10h]
0x180008fcb  cmp     qword ptr [r9+18h], 7
0x180008fd0  jbe     short loc_180008FD5
0x180008fd2  mov     r9, [r9]
0x180008fd5  lea     r8, aWin32_0; "WIN32"
0x180008fdc  mov     rcx, [rcx+38h]
0x180008fe0  jmp     short loc_180009016
0x180008fe2  mov     edx, [rcx+40h]
0x180008fe5  test    edx, edx
0x180008fe7  jz      short loc_180009006
0x180008fe9  cmp     [rcx+9], r9b
0x180008fed  jz      short loc_180008FFD
0x180008fef  lea     r9, [rcx+10h]
0x180008ff3  cmp     qword ptr [r9+18h], 7
0x180008ff8  jbe     short loc_180008FFD
0x180008ffa  mov     r9, [r9]
0x180008ffd  lea     r8, aHresult_0; "HRESULT"
0x180009004  jmp     short loc_180008FDC
0x180009006  mov     rcx, [rcx+38h]; context
0x18000900a  mov     edx, 1; resultCode
0x18000900f  lea     r8, resultType; "MI"
0x180009016  call    MI_Context_PostError
0x18000901b  add     rsp, 28h
0x18000901f  retn
```
