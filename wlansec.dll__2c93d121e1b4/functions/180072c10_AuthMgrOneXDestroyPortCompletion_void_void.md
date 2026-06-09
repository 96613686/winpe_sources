# AuthMgrOneXDestroyPortCompletion(void *,void *)

- ea: `0x180072c10`
- end: `0x180072ea4`
- name: `?AuthMgrOneXDestroyPortCompletion@@YAKPEAX0@Z`
- size: `660`
- prototype: `unsigned int __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180013600`
- `0x1800163e0`
- `0x180025a70`
- `0x18002bb08`
- `0x1800328b0`
- `0x18003b104`
- `0x180072c10`

## import_xrefs

- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180072de0`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180072de0`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180072c9b`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180072c9b`

## string_xrefs

- `0x180072c33`: `AuthMgrOneXDestroyPortCompletion`
- `0x180072dbd`: `AuthMgrOneXDestroyPortCompletion`
- `0x180072e81`: `AuthMgrOneXDestroyPortCompletion`

## pseudocode

```c
__int64 __fastcall AuthMgrOneXDestroyPortCompletion(void *a1, void *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  PVOID *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rdi
  PVOID *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax
  void *v13; // [rsp+50h] [rbp+8h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = a1;
  v14 = 0;
  IncThreadCountEx("AuthMgrOneXDestroyPortCompletion", 1145);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 102, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  v3 = HtReferenceHandleWithTag(qword_1800AEFA8, a1, 2, 0, 1, &v14);
  v4 = v14;
  if ( !v14 )
  {
    if ( !v3 )
      v3 = 1168;
LABEL_8:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_38;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v6 = 103;
      v7 = v3;
LABEL_27:
      WPP_SF_d(v5[7], v6, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v7);
LABEL_28:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_29;
    }
    goto LABEL_29;
  }
  if ( v3 )
    goto LABEL_8;
  v8 = *(_QWORD *)(v14 + 16);
  if ( v8 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        105,
        WPP_20060763357235bdafa6f501eee46e60_Traceguids,
        *(unsigned int *)(v8 + 312));
      v4 = v14;
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *(void **)(v8 + 944) == a1 )
    {
      *(_QWORD *)(v4 + 16) = 0;
      *(_QWORD *)(v8 + 944) = 0;
      TracePortId(*(_DWORD *)(v8 + 312), "<<< Derefing <<<");
      SecMgrDerefPortEx((struct MSMSEC_PORT_CONTEXT *)v8, "AuthMgrOneXDestroyPortCompletion", 1201);
    }
    else
    {
      v3 = 1168;
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
        WPP_SF_qq(v9[7], 106, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
    }
  }
  else
  {
    v3 = 1168;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 104, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  }
  v10 = HtDereferenceHandleWithTag(qword_1800AEFA8, a1, 2);
  if ( !v10 )
    goto LABEL_28;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v6 = 107;
    v7 = v10;
    goto LABEL_27;
  }
LABEL_29:
  if ( !v3 )
  {
    v11 = RemoveHandleTableEntry(&v13);
    if ( v11 )
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_38;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_35;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 108, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v11);
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_35:
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x100) != 0 )
    WPP_SF_d(v5[7], 109, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v3);
LABEL_38:
  DecThreadCountEx("AuthMgrOneXDestroyPortCompletion", 1220);
  return v3;
}

```

## disassembly

```asm
0x180072c10  mov     rax, rsp
0x180072c13  mov     [rax+10h], rbx
0x180072c17  mov     [rax+20h], rsi
0x180072c1b  mov     [rax+8], rcx
0x180072c1f  push    rdi
0x180072c20  push    r14
0x180072c22  push    r15
0x180072c24  sub     rsp, 30h
0x180072c28  mov     rsi, rcx
0x180072c2b  mov     qword ptr [rax+18h], 0
0x180072c33  lea     rcx, aAuthmgronexdes; "AuthMgrOneXDestroyPortCompletion"
0x180072c3a  mov     edx, 479h; int
0x180072c3f  call    ?IncThreadCountEx@@YAXPEBDH@Z; IncThreadCountEx(char const *,int)
0x180072c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180072c4b  lea     r14, WPP_GLOBAL_Control
0x180072c52  lea     r15, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180072c59  cmp     rcx, r14
0x180072c5c  jz      short loc_180072C78
0x180072c5e  test    dword ptr [rcx+44h], 100h
0x180072c65  jz      short loc_180072C78
0x180072c67  mov     rcx, [rcx+38h]
0x180072c6b  mov     edx, 66h ; 'f'
0x180072c70  mov     r8, r15
0x180072c73  call    WPP_SF_
0x180072c78  mov     rcx, cs:qword_1800AEFA8
0x180072c7f  lea     rax, [rsp+48h+arg_10]
0x180072c84  xor     r9d, r9d
0x180072c87  mov     [rsp+48h+var_20], rax
0x180072c8c  mov     rdx, rsi
0x180072c8f  mov     dword ptr [rsp+48h+var_28], 1
0x180072c97  lea     r8d, [r9+2]
0x180072c9b  call    cs:__imp_HtReferenceHandleWithTag
0x180072ca2  nop     dword ptr [rax+rax+00h]
0x180072ca7  mov     ebx, eax
0x180072ca9  mov     rax, [rsp+48h+arg_10]
0x180072cae  test    rax, rax
0x180072cb1  jnz     short loc_180072CBE
0x180072cb3  test    ebx, ebx
0x180072cb5  jnz     short loc_180072CC2
0x180072cb7  mov     ebx, 490h
0x180072cbc  jmp     short loc_180072CC2
0x180072cbe  test    ebx, ebx
0x180072cc0  jz      short loc_180072CE9
0x180072cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180072cc9  cmp     rcx, r14
0x180072ccc  jz      loc_180072E7C
0x180072cd2  test    byte ptr [rcx+44h], 1
0x180072cd6  jz      loc_180072E1D
0x180072cdc  mov     edx, 67h ; 'g'
0x180072ce1  mov     r9d, ebx
0x180072ce4  jmp     loc_180072E0A
0x180072ce9  mov     rdi, [rax+10h]
0x180072ced  test    rdi, rdi
0x180072cf0  jnz     short loc_180072D25
0x180072cf2  mov     ebx, 490h
0x180072cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180072cfe  cmp     rcx, r14
0x180072d01  jz      loc_180072DCC
0x180072d07  test    byte ptr [rcx+44h], 1
0x180072d0b  jz      loc_180072DCC
0x180072d11  mov     rcx, [rcx+38h]
0x180072d15  lea     edx, [rdi+68h]
0x180072d18  mov     r8, r15
0x180072d1b  call    WPP_SF_
0x180072d20  jmp     loc_180072DCC
0x180072d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180072d2c  cmp     rcx, r14
0x180072d2f  jz      short loc_180072D5B
0x180072d31  test    byte ptr [rcx+44h], 20h
0x180072d35  jz      short loc_180072D5B
0x180072d37  mov     r9d, [rdi+138h]
0x180072d3e  mov     edx, 69h ; 'i'
0x180072d43  mov     rcx, [rcx+38h]
0x180072d47  mov     r8, r15
0x180072d4a  call    WPP_SF_d
0x180072d4f  mov     rax, [rsp+48h+arg_10]
0x180072d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180072d5b  mov     r8, [rdi+3B0h]
0x180072d62  cmp     r8, rsi
0x180072d65  jz      short loc_180072D92
0x180072d67  mov     ebx, 490h
0x180072d6c  cmp     rcx, r14
0x180072d6f  jz      short loc_180072DCC
0x180072d71  test    byte ptr [rcx+44h], 1
0x180072d75  jz      short loc_180072DCC
0x180072d77  mov     rcx, [rcx+38h]
0x180072d7b  mov     edx, 6Ah ; 'j'
0x180072d80  mov     [rsp+48h+var_28], r8
0x180072d85  mov     r9, rsi
0x180072d88  mov     r8, r15
0x180072d8b  call    WPP_SF_qq
0x180072d90  jmp     short loc_180072DCC
0x180072d92  mov     qword ptr [rax+10h], 0
0x180072d9a  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180072da1  mov     qword ptr [rdi+3B0h], 0
0x180072dac  mov     ecx, [rdi+138h]; unsigned int
0x180072db2  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180072db7  mov     r8d, 4B1h; int
0x180072dbd  lea     rdx, aAuthmgronexdes; "AuthMgrOneXDestroyPortCompletion"
0x180072dc4  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180072dc7  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180072dcc  mov     rcx, cs:qword_1800AEFA8
0x180072dd3  mov     r9d, 1
0x180072dd9  mov     rdx, rsi
0x180072ddc  lea     r8d, [r9+1]
0x180072de0  call    cs:__imp_HtDereferenceHandleWithTag
0x180072de7  nop     dword ptr [rax+rax+00h]
0x180072dec  test    eax, eax
0x180072dee  jz      short loc_180072E16
0x180072df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180072df7  cmp     rcx, r14
0x180072dfa  jz      short loc_180072E1D
0x180072dfc  test    byte ptr [rcx+44h], 1
0x180072e00  jz      short loc_180072E1D
0x180072e02  mov     edx, 6Bh ; 'k'
0x180072e07  mov     r9d, eax
0x180072e0a  mov     rcx, [rcx+38h]
0x180072e0e  mov     r8, r15
0x180072e11  call    WPP_SF_d
0x180072e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e1d  test    ebx, ebx
0x180072e1f  jnz     short loc_180072E5A
0x180072e21  lea     rcx, [rsp+48h+arg_0]; void **
0x180072e26  call    ?RemoveHandleTableEntry@@YAKPEAPEAX@Z; RemoveHandleTableEntry(void * *)
0x180072e2b  test    eax, eax
0x180072e2d  jz      short loc_180072E53
0x180072e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e36  cmp     rcx, r14
0x180072e39  jz      short loc_180072E7C
0x180072e3b  test    byte ptr [rcx+44h], 1
0x180072e3f  jz      short loc_180072E5A
0x180072e41  mov     rcx, [rcx+38h]
0x180072e45  lea     edx, [rbx+6Ch]
0x180072e48  mov     r9d, eax
0x180072e4b  mov     r8, r15
0x180072e4e  call    WPP_SF_d
0x180072e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e5a  cmp     rcx, r14
0x180072e5d  jz      short loc_180072E7C
0x180072e5f  test    dword ptr [rcx+44h], 100h
0x180072e66  jz      short loc_180072E7C
0x180072e68  mov     rcx, [rcx+38h]
0x180072e6c  mov     edx, 6Dh ; 'm'
0x180072e71  mov     r9d, ebx
0x180072e74  mov     r8, r15
0x180072e77  call    WPP_SF_d
0x180072e7c  mov     edx, 4C4h; int
0x180072e81  lea     rcx, aAuthmgronexdes; "AuthMgrOneXDestroyPortCompletion"
0x180072e88  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180072e8d  mov     rsi, [rsp+48h+arg_18]
0x180072e92  mov     eax, ebx
0x180072e94  mov     rbx, [rsp+48h+arg_8]
0x180072e99  add     rsp, 30h
0x180072e9d  pop     r15
0x180072e9f  pop     r14
0x180072ea1  pop     rdi
0x180072ea2  retn
```
