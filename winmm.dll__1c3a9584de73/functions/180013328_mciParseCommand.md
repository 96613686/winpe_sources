# mciParseCommand

- ea: `0x180013328`
- end: `0x1800133ff`
- name: `mciParseCommand`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010504`

## callees

- `0x18000b6d4`
- `0x180011020`
- `0x180012a50`
- `0x180013328`

## pseudocode

```c
const WCHAR *__fastcall mciParseCommand(
        unsigned int a1,
        const WCHAR *a2,
        const wchar_t *a3,
        const WCHAR **a4,
        unsigned int *a5)
{
  const wchar_t *v8; // r9
  const WCHAR *result; // rax
  _DWORD v10[14]; // [rsp+30h] [rbp-38h] BYREF

  v10[0] = 0;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LODWORD(v8) = (_DWORD)a2;
    if ( !a3 )
      a3 = L"(NULL)";
    if ( !a2 )
      v8 = L"(NULL)";
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      (unsigned int)WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids,
      (_DWORD)v8,
      (__int64)a3);
  }
  result = FindCommandItem(a1, (__int64)a2, a2, v10, a5);
  if ( result )
  {
    if ( a4 )
    {
      *a4 = result;
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids);
    }
    return (const WCHAR *)v10[0];
  }
  return result;
}

```

## disassembly

```asm
0x180013328  push    rbx
0x18001332a  push    rsi
0x18001332b  push    rdi
0x18001332c  push    r14
0x18001332e  sub     rsp, 48h
0x180013332  mov     rbx, r9
0x180013335  mov     [rsp+68h+var_38], 0
0x18001333d  mov     rdi, rdx
0x180013340  mov     esi, ecx
0x180013342  mov     rcx, cs:WPP_GLOBAL_Control
0x180013349  lea     r14, WPP_GLOBAL_Control
0x180013350  cmp     rcx, r14
0x180013353  jz      short loc_180013396
0x180013355  test    dword ptr [rcx+1Ch], 400000h
0x18001335c  jz      short loc_180013396
0x18001335e  cmp     byte ptr [rcx+19h], 2
0x180013362  jb      short loc_180013396
0x180013364  mov     rcx, [rcx+10h]
0x180013368  lea     rax, aNull; "(NULL)"
0x18001336f  test    r8, r8
0x180013372  mov     r9, rdx
0x180013375  cmovz   r8, rax
0x180013379  test    rdx, rdx
0x18001337c  mov     [rsp+68h+var_48], r8
0x180013381  mov     edx, 3Eh ; '>'
0x180013386  cmovz   r9, rax
0x18001338a  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180013391  call    WPP_SF_SS
0x180013396  mov     rax, [rsp+68h+arg_20]
0x18001339e  lea     r9, [rsp+68h+var_38]
0x1800133a3  mov     r8, rdi
0x1800133a6  mov     [rsp+68h+var_48], rax
0x1800133ab  mov     ecx, esi
0x1800133ad  call    FindCommandItem
0x1800133b2  test    rax, rax
0x1800133b5  jz      short loc_1800133F5
0x1800133b7  test    rbx, rbx
0x1800133ba  jz      short loc_1800133C1
0x1800133bc  mov     [rbx], rax
0x1800133bf  jmp     short loc_1800133F1
0x1800133c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133c8  cmp     rcx, r14
0x1800133cb  jz      short loc_1800133F1
0x1800133cd  test    dword ptr [rcx+1Ch], 400000h
0x1800133d4  jz      short loc_1800133F1
0x1800133d6  cmp     byte ptr [rcx+19h], 1
0x1800133da  jb      short loc_1800133F1
0x1800133dc  mov     rcx, [rcx+10h]
0x1800133e0  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x1800133e7  mov     edx, 3Fh ; '?'
0x1800133ec  call    WPP_SF_
0x1800133f1  mov     eax, [rsp+68h+var_38]
0x1800133f5  add     rsp, 48h
0x1800133f9  pop     r14
0x1800133fb  pop     rdi
0x1800133fc  pop     rsi
0x1800133fd  pop     rbx
0x1800133fe  retn
```
