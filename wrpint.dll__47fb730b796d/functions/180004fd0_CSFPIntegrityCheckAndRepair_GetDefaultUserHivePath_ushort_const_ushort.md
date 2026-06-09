# CSFPIntegrityCheckAndRepair::GetDefaultUserHivePath(ushort const *,ushort * *)

- ea: `0x180004fd0`
- end: `0x1800051e9`
- name: `?GetDefaultUserHivePath@CSFPIntegrityCheckAndRepair@@EEAAJPEBGPEAPEAG@Z`
- size: `537`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001de0`
- `0x180004fd0`
- `0x180007288`
- `0x180010448`
- `0x180010de4`
- `0x180011248`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800050b7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800050b7`

## string_xrefs

- `0x180004ffd`: `ProfilesDirectory`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::GetDefaultUserHivePath(
        CSFPIntegrityCheckAndRepair *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v3; // rcx
  unsigned __int16 *v6; // rdi
  signed int v7; // ebx
  PCNZWCH v8; // rsi
  PCNZWCH v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  unsigned __int16 *v14; // rcx
  unsigned __int16 v15; // ax
  unsigned __int16 *v17; // [rsp+60h] [rbp+8h] BYREF
  PCNZWCH lpString2; // [rsp+78h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 4);
  lpString2 = 0;
  v17 = 0;
  v6 = 0;
  v7 = WrpRegQueryStringValue(
         v3,
         L"Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         L"ProfilesDirectory",
         &lpString2);
  if ( v7 < 0 || (v7 = SczEnsureBackslashTerminated(&lpString2), v7 < 0) )
  {
    v8 = lpString2;
    goto LABEL_30;
  }
  v8 = lpString2;
  if ( !lpString2 )
    goto LABEL_27;
  v9 = lpString2;
  v10 = 0x7FFFFFFF;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v7 = v10 == 0 ? 0x80070057 : 0;
  if ( !v10 )
    goto LABEL_30;
  if ( ((0x7FFFFFFF - v10) & (unsigned __int64)-(__int64)(v10 != 0)) < 0xD
    || *lpString2 != 37
    || CompareStringW(0x7Fu, 1u, L"%SystemDrive%", 13, lpString2, 13) != 2 )
  {
    v7 = -2147467259;
    goto LABEL_30;
  }
  v7 = SczAllocFromSz(&v17, a2);
  if ( v7 < 0 )
  {
LABEL_28:
    v6 = v17;
    goto LABEL_30;
  }
  v6 = v17;
  if ( !v17 )
  {
LABEL_27:
    v7 = -2147024809;
    goto LABEL_30;
  }
  v11 = 0x7FFFFFFF;
  v12 = v17;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v7 = v11 == 0 ? 0x80070057 : 0;
  v13 = (0x7FFFFFFF - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64);
  if ( v11 )
  {
    v14 = &v17[v13 - 1];
    if ( *v14 != 92 && *v14 != 47 || (v14 = &v17[v13 - 2], *v14 != 92) )
    {
      v15 = *v14;
      do
      {
        if ( v15 == 47 )
          break;
        if ( v14 == v17 )
          goto LABEL_27;
        v15 = *--v14;
      }
      while ( *v14 != 92 );
    }
    *v14 = 0;
    v7 = SczAllocConcat2Sz(&v17, v8 + 13, L"default\\");
    if ( v7 >= 0 )
    {
      v6 = 0;
      *a3 = v17;
      v7 = 0;
      goto LABEL_30;
    }
    goto LABEL_28;
  }
LABEL_30:
  if ( v8 )
    operator delete((void *)(v8 - 4));
  if ( v6 )
    operator delete(v6 - 4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004fd0  mov     rax, rsp
0x180004fd3  mov     [rax+10h], rbx
0x180004fd7  mov     [rax+18h], rsi
0x180004fdb  push    rdi
0x180004fdc  push    r12
0x180004fde  push    r13
0x180004fe0  push    r14
0x180004fe2  push    r15
0x180004fe4  sub     rsp, 30h
0x180004fe8  mov     rcx, [rcx+20h]
0x180004fec  lea     r9, [rax+20h]
0x180004ff0  xor     r13d, r13d
0x180004ff3  mov     r12, r8
0x180004ff6  mov     r15, rdx
0x180004ff9  mov     [rax+20h], r13
0x180004ffd  lea     r8, aProfilesdirect; "ProfilesDirectory"
0x180005004  mov     [rax+8], r13
0x180005008  lea     rdx, aMicrosoftWindo_0; "Microsoft\\Windows NT\\CurrentVersion\\"...
0x18000500f  mov     edi, r13d
0x180005012  call    WrpRegQueryStringValue
0x180005017  mov     ebx, eax
0x180005019  test    eax, eax
0x18000501b  js      loc_1800051AE
0x180005021  lea     rcx, [rsp+58h+arg_18]
0x180005026  call    SczEnsureBackslashTerminated
0x18000502b  mov     ebx, eax
0x18000502d  test    eax, eax
0x18000502f  js      loc_1800051AE
0x180005035  mov     rsi, [rsp+58h+arg_18]
0x18000503a  test    rsi, rsi
0x18000503d  jz      loc_1800051A0
0x180005043  mov     r14d, 7FFFFFFFh
0x180005049  mov     rax, rsi
0x18000504c  mov     edx, r14d
0x18000504f  cmp     [rax], r13w
0x180005053  jz      short loc_18000505F
0x180005055  add     rax, 2
0x180005059  sub     rdx, 1
0x18000505d  jnz     short loc_18000504F
0x18000505f  mov     rax, rdx
0x180005062  mov     rcx, r14
0x180005065  neg     rax
0x180005068  mov     rax, rdx
0x18000506b  sbb     ebx, ebx
0x18000506d  sub     rcx, rdx
0x180005070  not     ebx
0x180005072  and     ebx, 80070057h
0x180005078  neg     rax
0x18000507b  sbb     r8, r8
0x18000507e  and     r8, rcx
0x180005081  test    rdx, rdx
0x180005084  jz      loc_1800051B3
0x18000508a  cmp     r8, 0Dh
0x18000508e  jb      short loc_1800050C1
0x180005090  cmp     word ptr [rsi], 25h ; '%'
0x180005094  jnz     short loc_1800050C1
0x180005096  mov     r9d, 0Dh; cchCount1
0x18000509c  mov     [rsp+58h+cchCount2], 0Dh; cchCount2
0x1800050a4  lea     r8, String1; "%SystemDrive%"
0x1800050ab  mov     [rsp+58h+lpString2], rsi; lpString2
0x1800050b0  lea     edx, [r9-0Ch]; dwCmpFlags
0x1800050b4  lea     ecx, [rdx+7Eh]; Locale
0x1800050b7  call    cs:__imp_CompareStringW
0x1800050bd  test    eax, eax
0x1800050bf  jnz     short loc_1800050CB
0x1800050c1  mov     ebx, 80004005h
0x1800050c6  jmp     loc_1800051B3
0x1800050cb  cmp     eax, 2
0x1800050ce  jnz     short loc_1800050C1
0x1800050d0  mov     rdx, r15
0x1800050d3  lea     rcx, [rsp+58h+arg_0]
0x1800050d8  call    SczAllocFromSz
0x1800050dd  mov     ebx, eax
0x1800050df  test    eax, eax
0x1800050e1  js      loc_1800051A7
0x1800050e7  mov     rdi, [rsp+58h+arg_0]
0x1800050ec  test    rdi, rdi
0x1800050ef  jz      loc_1800051A0
0x1800050f5  mov     rcx, r14
0x1800050f8  mov     rax, rdi
0x1800050fb  cmp     [rax], r13w
0x1800050ff  jz      short loc_18000510B
0x180005101  add     rax, 2
0x180005105  sub     rcx, 1
0x180005109  jnz     short loc_1800050FB
0x18000510b  mov     rax, rcx
0x18000510e  neg     rax
0x180005111  mov     rax, rcx
0x180005114  sbb     ebx, ebx
0x180005116  sub     r14, rcx
0x180005119  not     ebx
0x18000511b  and     ebx, 80070057h
0x180005121  neg     rax
0x180005124  sbb     rdx, rdx
0x180005127  and     rdx, r14
0x18000512a  test    rcx, rcx
0x18000512d  jz      loc_1800051B3
0x180005133  lea     rcx, [rdi-2]
0x180005137  lea     rcx, [rcx+rdx*2]
0x18000513b  cmp     word ptr [rcx], 5Ch ; '\'
0x18000513f  jz      short loc_180005147
0x180005141  cmp     word ptr [rcx], 2Fh ; '/'
0x180005145  jnz     short loc_180005155
0x180005147  lea     rcx, [rdi-4]
0x18000514b  lea     rcx, [rcx+rdx*2]
0x18000514f  cmp     word ptr [rcx], 5Ch ; '\'
0x180005153  jz      short loc_180005170
0x180005155  movzx   eax, word ptr [rcx]
0x180005158  cmp     ax, 2Fh ; '/'
0x18000515c  jz      short loc_180005170
0x18000515e  cmp     rcx, rdi
0x180005161  jz      short loc_1800051A0
0x180005163  sub     rcx, 2
0x180005167  movzx   eax, word ptr [rcx]
0x18000516a  cmp     ax, 5Ch ; '\'
0x18000516e  jnz     short loc_180005158
0x180005170  mov     [rcx], r13w
0x180005174  lea     rdx, [rsi+1Ah]
0x180005178  lea     rcx, [rsp+58h+arg_0]
0x18000517d  lea     r8, aDefault_0; "default\\"
0x180005184  call    SczAllocConcat2Sz
0x180005189  mov     ebx, eax
0x18000518b  test    eax, eax
0x18000518d  js      short loc_1800051A7
0x18000518f  mov     rax, [rsp+58h+arg_0]
0x180005194  mov     rdi, r13
0x180005197  mov     [r12], rax
0x18000519b  mov     ebx, r13d
0x18000519e  jmp     short loc_1800051B3
0x1800051a0  mov     ebx, 80070057h
0x1800051a5  jmp     short loc_1800051B3
0x1800051a7  mov     rdi, [rsp+58h+arg_0]
0x1800051ac  jmp     short loc_1800051B3
0x1800051ae  mov     rsi, [rsp+58h+arg_18]
0x1800051b3  test    rsi, rsi
0x1800051b6  jz      short loc_1800051C1
0x1800051b8  lea     rcx, [rsi-8]; Block
0x1800051bc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800051c1  test    rdi, rdi
0x1800051c4  jz      short loc_1800051CF
0x1800051c6  lea     rcx, [rdi-8]; Block
0x1800051ca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800051cf  mov     rsi, [rsp+58h+arg_10]
0x1800051d4  mov     eax, ebx
0x1800051d6  mov     rbx, [rsp+58h+arg_8]
0x1800051db  add     rsp, 30h
0x1800051df  pop     r15
0x1800051e1  pop     r14
0x1800051e3  pop     r13
0x1800051e5  pop     r12
0x1800051e7  pop     rdi
0x1800051e8  retn
```
