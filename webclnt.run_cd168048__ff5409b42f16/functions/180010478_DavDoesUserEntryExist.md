# DavDoesUserEntryExist

- ea: `0x180010478`
- end: `0x180010769`
- name: `DavDoesUserEntryExist`
- size: `753`
- prototype: `__int64 __usercall@<rax>(HLOCAL hMem@<rcx>, __int64)`
- caller_count: `12`
- callee_count: `8`
- tags: ``

## callers

- `0x180009740`
- `0x18000b060`
- `0x1800196d0`
- `0x18001a5a0`
- `0x18001ca70`
- `0x18001db70`
- `0x18001dfc0`
- `0x18001ead0`
- `0x18001f190`
- `0x180023360`
- `0x180023960`
- `0x180024190`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18000b99c`
- `0x18000bc5c`
- `0x18000fce0`
- `0x180010478`
- `0x1800117f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001051b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001051b`
- `KERNEL32!LocalFree` at `0x180010630`
- `KERNEL32!LocalFree` at `0x180010630`
- `KERNEL32!LocalAlloc` at `0x1800104bc`
- `KERNEL32!LocalAlloc` at `0x1800104bc`

## pseudocode

```c
__int64 __fastcall DavDoesUserEntryExist(wchar_t *hMem, int a2, _DWORD *a3, __int64 **a4, __int64 **a5)
{
  wchar_t *v8; // rdi
  unsigned int v9; // r12d
  unsigned int v10; // eax
  wchar_t *v11; // rsi
  __int64 v12; // rbx
  DWORD LastError; // eax
  DWORD v14; // eax
  _QWORD *v15; // rcx
  __int64 *v16; // rcx
  __int64 *i; // rax
  __int64 *v18; // rbx
  _QWORD *v20; // rcx
  __int64 *v21; // r8
  __int64 *v22; // rdx
  __int64 *v23; // rbx

  v8 = hMem;
  v9 = 0;
  v10 = DavConvertIDNToPunyCode(hMem);
  if ( v10 )
  {
    v11 = (wchar_t *)LocalAlloc(0x40u, 2LL * v10);
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_d(v12, 133, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
      }
      *a5 = 0;
      return v9;
    }
    DavConvertIDNToPunyCode(v8);
    v14 = GetLastError();
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v14);
      goto LABEL_29;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x87u,
        (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
        v11);
      v15 = WPP_GLOBAL_Control;
    }
    v8 = v11;
  }
  else
  {
    v15 = WPP_GLOBAL_Control;
    v11 = 0;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
    WPP_SF_Sd(v15[2], 136, (unsigned int)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, (_DWORD)v8, a2);
  v16 = &ServerHashTable[2 * (unsigned int)DavHashTheServerName(v8)];
  for ( i = (__int64 *)*v16; ; i = (__int64 *)*i )
  {
    if ( i == v16 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0x8Au,
          (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
          v8);
      *a5 = 0;
LABEL_27:
      *a4 = 0;
      goto LABEL_28;
    }
    v18 = i - 11;
    if ( a2 == *((_DWORD *)i - 20) )
      break;
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x89u, (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v8);
    v20 = WPP_GLOBAL_Control;
  }
  *a5 = v18;
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 2) != 0 )
  {
    WPP_SF_q(v20[2], 139, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v18);
    v20 = WPP_GLOBAL_Control;
  }
  v21 = v18 + 9;
  v22 = (__int64 *)v18[9];
  if ( v22 == v18 + 9 )
  {
LABEL_41:
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 2) != 0 )
      WPP_SF_(v20[2], 141, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
    goto LABEL_27;
  }
  while ( 1 )
  {
    v23 = v22 - 2;
    if ( *((_DWORD *)v22 - 4) == *a3 && *((_DWORD *)v23 + 1) == a3[1] )
      break;
    v22 = (__int64 *)*v22;
    if ( v22 == v21 )
      goto LABEL_41;
  }
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 2) != 0 )
  {
    WPP_SF_(v20[2], 140, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
    v20 = WPP_GLOBAL_Control;
  }
  v9 = 1;
  *a4 = v23;
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 2) != 0 )
    WPP_SF_q(v20[2], 142, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v23);
LABEL_28:
  if ( v11 )
LABEL_29:
    LocalFree(v11);
  return v9;
}

```

## disassembly

```asm
0x180010478  push    rbx
0x18001047a  push    rbp
0x18001047b  push    rsi
0x18001047c  push    rdi
0x18001047d  push    r12
0x18001047f  push    r13
0x180010481  push    r14
0x180010483  push    r15
0x180010485  sub     rsp, 38h
0x180010489  mov     r15, r8
0x18001048c  mov     ebp, edx
0x18001048e  xor     r8d, r8d
0x180010491  xor     edx, edx
0x180010493  mov     r14, r9
0x180010496  mov     rdi, rcx
0x180010499  xor     r12d, r12d
0x18001049c  call    DavConvertIDNToPunyCode
0x1800104a1  mov     ebx, eax
0x1800104a3  lea     r13, WPP_GLOBAL_Control
0x1800104aa  test    eax, eax
0x1800104ac  jz      loc_180010592
0x1800104b2  mov     edx, ebx
0x1800104b4  lea     ecx, [r12+40h]; uFlags
0x1800104b9  add     rdx, rdx; uBytes
0x1800104bc  call    cs:__imp_LocalAlloc
0x1800104c2  mov     rsi, rax
0x1800104c5  test    rax, rax
0x1800104c8  jnz     short loc_18001050D
0x1800104ca  mov     rbx, cs:WPP_GLOBAL_Control
0x1800104d1  cmp     rbx, r13
0x1800104d4  jz      short loc_1800104FD
0x1800104d6  test    byte ptr [rbx+1Ch], 1
0x1800104da  jz      short loc_1800104FD
0x1800104dc  mov     rbx, [rbx+10h]
0x1800104e0  call    cs:__imp_GetLastError
0x1800104e6  mov     edx, 85h
0x1800104eb  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800104f2  mov     r9d, eax
0x1800104f5  mov     rcx, rbx
0x1800104f8  call    WPP_SF_d
0x1800104fd  mov     rax, [rsp+78h+arg_20]
0x180010505  mov     [rax], r12
0x180010508  jmp     loc_180010636
0x18001050d  mov     r8d, ebx
0x180010510  mov     rdx, rsi
0x180010513  mov     rcx, rdi; hMem
0x180010516  call    DavConvertIDNToPunyCode
0x18001051b  call    cs:__imp_GetLastError
0x180010521  test    eax, eax
0x180010523  jz      short loc_18001055C
0x180010525  mov     rcx, cs:WPP_GLOBAL_Control
0x18001052c  cmp     rcx, r13
0x18001052f  jz      loc_18001062D
0x180010535  test    byte ptr [rcx+1Ch], 1
0x180010539  jz      loc_18001062D
0x18001053f  mov     rcx, [rcx+10h]
0x180010543  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001054a  mov     edx, 86h
0x18001054f  mov     r9d, eax
0x180010552  call    WPP_SF_d
0x180010557  jmp     loc_18001062D
0x18001055c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010563  cmp     rcx, r13
0x180010566  jz      short loc_18001058D
0x180010568  test    byte ptr [rcx+1Ch], 2
0x18001056c  jz      short loc_18001058D
0x18001056e  mov     rcx, [rcx+10h]
0x180010572  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010579  mov     edx, 87h
0x18001057e  mov     r9, rsi
0x180010581  call    WPP_SF_S
0x180010586  mov     rcx, cs:WPP_GLOBAL_Control
0x18001058d  mov     rdi, rsi
0x180010590  jmp     short loc_18001059B
0x180010592  mov     rcx, cs:WPP_GLOBAL_Control
0x180010599  xor     esi, esi
0x18001059b  cmp     rcx, r13
0x18001059e  jz      short loc_1800105C2
0x1800105a0  test    byte ptr [rcx+1Ch], 2
0x1800105a4  jz      short loc_1800105C2
0x1800105a6  mov     rcx, [rcx+10h]
0x1800105aa  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800105b1  mov     edx, 88h
0x1800105b6  mov     [rsp+78h+var_58], ebp
0x1800105ba  mov     r9, rdi
0x1800105bd  call    WPP_SF_Sd
0x1800105c2  mov     rcx, rdi
0x1800105c5  call    DavHashTheServerName
0x1800105ca  mov     eax, eax
0x1800105cc  lea     rcx, ServerHashTable
0x1800105d3  shl     rax, 4
0x1800105d7  add     rcx, rax
0x1800105da  mov     rax, [rcx]
0x1800105dd  jmp     short loc_1800105EB
0x1800105df  lea     rbx, [rax-58h]
0x1800105e3  cmp     ebp, [rbx+8]
0x1800105e6  jz      short loc_18001064A
0x1800105e8  mov     rax, [rax]
0x1800105eb  cmp     rax, rcx
0x1800105ee  jnz     short loc_1800105DF
0x1800105f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105f7  cmp     rcx, r13
0x1800105fa  jz      short loc_18001061A
0x1800105fc  test    byte ptr [rcx+1Ch], 2
0x180010600  jz      short loc_18001061A
0x180010602  mov     rcx, [rcx+10h]
0x180010606  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001060d  mov     edx, 8Ah
0x180010612  mov     r9, rdi
0x180010615  call    WPP_SF_S
0x18001061a  mov     rcx, [rsp+78h+arg_20]
0x180010622  mov     [rcx], r12
0x180010625  mov     [r14], r12
0x180010628  test    rsi, rsi
0x18001062b  jz      short loc_180010636
0x18001062d  mov     rcx, rsi; hMem
0x180010630  call    cs:__imp_LocalFree
0x180010636  mov     eax, r12d
0x180010639  add     rsp, 38h
0x18001063d  pop     r15
0x18001063f  pop     r14
0x180010641  pop     r13
0x180010643  pop     r12
0x180010645  pop     rdi
0x180010646  pop     rsi
0x180010647  pop     rbp
0x180010648  pop     rbx
0x180010649  retn
0x18001064a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010651  mov     bpl, 2
0x180010654  cmp     rcx, r13
0x180010657  jz      short loc_18001067E
0x180010659  test    [rcx+1Ch], bpl
0x18001065d  jz      short loc_18001067E
0x18001065f  mov     rcx, [rcx+10h]
0x180010663  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001066a  mov     edx, 89h
0x18001066f  mov     r9, rdi
0x180010672  call    WPP_SF_S
0x180010677  mov     rcx, cs:WPP_GLOBAL_Control
0x18001067e  mov     rax, [rsp+78h+arg_20]
0x180010686  mov     [rax], rbx
0x180010689  cmp     rcx, r13
0x18001068c  jz      short loc_1800106B3
0x18001068e  test    [rcx+1Ch], bpl
0x180010692  jz      short loc_1800106B3
0x180010694  mov     rcx, [rcx+10h]
0x180010698  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001069f  mov     edx, 8Bh
0x1800106a4  mov     r9, rbx
0x1800106a7  call    WPP_SF_q
0x1800106ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106b3  lea     r8, [rbx+48h]
0x1800106b7  mov     rdx, [r8]
0x1800106ba  cmp     rdx, r8
0x1800106bd  jz      short loc_1800106DC
0x1800106bf  mov     r9d, [r15]
0x1800106c2  lea     rbx, [rdx-10h]
0x1800106c6  cmp     [rbx], r9d
0x1800106c9  jnz     short loc_1800106D4
0x1800106cb  mov     eax, [r15+4]
0x1800106cf  cmp     [rbx+4], eax
0x1800106d2  jz      short loc_180010709
0x1800106d4  mov     rdx, [rdx]
0x1800106d7  cmp     rdx, r8
0x1800106da  jnz     short loc_1800106C2
0x1800106dc  cmp     rcx, r13
0x1800106df  jz      loc_180010625
0x1800106e5  test    [rcx+1Ch], bpl
0x1800106e9  jz      loc_180010625
0x1800106ef  mov     rcx, [rcx+10h]
0x1800106f3  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800106fa  mov     edx, 8Dh
0x1800106ff  call    WPP_SF_
0x180010704  jmp     loc_180010625
0x180010709  cmp     rcx, r13
0x18001070c  jz      short loc_180010730
0x18001070e  test    [rcx+1Ch], bpl
0x180010712  jz      short loc_180010730
0x180010714  mov     rcx, [rcx+10h]
0x180010718  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001071f  mov     edx, 8Ch
0x180010724  call    WPP_SF_
0x180010729  mov     rcx, cs:WPP_GLOBAL_Control
0x180010730  mov     r12d, 1
0x180010736  mov     [r14], rbx
0x180010739  cmp     rcx, r13
0x18001073c  jz      loc_180010628
0x180010742  test    [rcx+1Ch], bpl
0x180010746  jz      loc_180010628
0x18001074c  mov     rcx, [rcx+10h]
0x180010750  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180010757  mov     edx, 8Eh
0x18001075c  mov     r9, rbx
0x18001075f  call    WPP_SF_q
0x180010764  jmp     loc_180010628
```
