# CVarVector::SetRawArrayData(void *,int,int)

- ea: `0x1800256c0`
- end: `0x1800257c3`
- name: `?SetRawArrayData@CVarVector@@QEAAJPEAXHH@Z`
- size: `259`
- prototype: `__int64 __fastcall(CVarVector *this, void *, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180013564`
- `0x180014120`
- `0x1800256c0`
- `0x18002ee96`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180025716`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180025716`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180025740`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180025740`

## pseudocode

```c
__int64 __fastcall CVarVector::SetRawArrayData(CVarVector *this, void *a2, int a3, int a4)
{
  __int64 v4; // rdi
  SAFEARRAY *v8; // rcx
  HRESULT v9; // ebx
  int v10; // ebx
  unsigned int v11; // edi
  void *v13; // [rsp+40h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 13);
  if ( !v4 )
  {
    v11 = -2147217407;
LABEL_13:
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v11);
    goto LABEL_9;
  }
  if ( a3 >= 0 && (unsigned int)a3 <= *(_DWORD *)(v4 + 24) && a4 == *(_DWORD *)(v4 + 20) )
  {
    v8 = *(SAFEARRAY **)(v4 + 32);
    v13 = 0;
    v9 = SafeArrayAccessData(v8, &v13);
    if ( v9 >= 0 )
    {
      memcpy_0(v13, a2, a4 * a3);
      *(_DWORD *)v4 = a3 - 1;
      SafeArrayUnaccessData(*(SAFEARRAY **)(v4 + 32));
    }
    v10 = (unsigned int)v9 >> 31;
  }
  else
  {
    v10 = 1;
  }
  v11 = v10 != 0 ? 0x80041001 : 0;
  if ( v10 )
    goto LABEL_13;
LABEL_9:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1800256c0  mov     rax, rsp
0x1800256c3  mov     [rax+10h], rbx
0x1800256c7  mov     [rax+18h], rbp
0x1800256cb  push    rsi
0x1800256cc  push    rdi
0x1800256cd  push    r14
0x1800256cf  sub     rsp, 20h
0x1800256d3  mov     rdi, [rcx+68h]
0x1800256d7  mov     ebp, r9d
0x1800256da  mov     esi, r8d
0x1800256dd  mov     r14, rdx
0x1800256e0  test    rdi, rdi
0x1800256e3  jz      loc_180025787
0x1800256e9  test    r8d, r8d
0x1800256ec  js      loc_18002579C
0x1800256f2  cmp     r8d, [rdi+18h]
0x1800256f6  ja      loc_18002579C
0x1800256fc  cmp     r9d, [rdi+14h]
0x180025700  jnz     loc_18002579C
0x180025706  mov     rcx, [rdi+20h]; psa
0x18002570a  lea     rdx, [rax+8]; ppvData
0x18002570e  mov     qword ptr [rax+8], 0
0x180025716  call    cs:__imp_SafeArrayAccessData
0x18002571c  mov     ebx, eax
0x18002571e  test    eax, eax
0x180025720  js      short loc_180025746
0x180025722  mov     ecx, esi
0x180025724  mov     rdx, r14; Src
0x180025727  imul    ecx, ebp
0x18002572a  movsxd  r8, ecx; Size
0x18002572d  mov     rcx, [rsp+38h+arg_0]; void *
0x180025732  call    memcpy_0
0x180025737  lea     ecx, [rsi-1]
0x18002573a  mov     [rdi], ecx
0x18002573c  mov     rcx, [rdi+20h]; psa
0x180025740  call    cs:__imp_SafeArrayUnaccessData
0x180025746  shr     ebx, 1Fh
0x180025749  mov     eax, ebx
0x18002574b  neg     eax
0x18002574d  sbb     edi, edi
0x18002574f  and     edi, 80041001h
0x180025755  test    ebx, ebx
0x180025757  jnz     short loc_18002578C
0x180025759  mov     rcx, cs:WPP_GLOBAL_Control
0x180025760  lea     rax, WPP_GLOBAL_Control
0x180025767  cmp     rcx, rax
0x18002576a  jz      short loc_180025772
0x18002576c  test    byte ptr [rcx+1Ch], 1
0x180025770  jnz     short loc_1800257A3
0x180025772  mov     rbx, [rsp+38h+arg_8]
0x180025777  mov     eax, edi
0x180025779  mov     rbp, [rsp+38h+arg_10]
0x18002577e  add     rsp, 20h
0x180025782  pop     r14
0x180025784  pop     rdi
0x180025785  pop     rsi
0x180025786  retn
0x180025787  mov     edi, 80041001h
0x18002578c  mov     edx, edi; int
0x18002578e  lea     rcx, qword_18006A9C0; this
0x180025795  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002579a  jmp     short loc_180025759
0x18002579c  mov     ebx, 1
0x1800257a1  jmp     short loc_180025749
0x1800257a3  cmp     byte ptr [rcx+19h], 2
0x1800257a7  jb      short loc_180025772
0x1800257a9  mov     rcx, [rcx+10h]
0x1800257ad  lea     r8, WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids
0x1800257b4  mov     edx, 4Dh ; 'M'
0x1800257b9  mov     r9d, edi
0x1800257bc  call    WPP_SF_D
0x1800257c1  jmp     short loc_180025772
```
