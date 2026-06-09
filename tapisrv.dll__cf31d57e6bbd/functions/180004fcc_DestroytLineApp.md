# DestroytLineApp

- ea: `0x180004fcc`
- end: `0x18000536f`
- name: `DestroytLineApp`
- size: `931`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180017500`
- `0x180026730`

## callees

- `0x180001600`
- `0x180004fcc`
- `0x180005378`
- `0x180006c14`
- `0x18001abb8`
- `0x18001c7c0`
- `0x180028b00`
- `0x18002c8d4`
- `0x18002d27c`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800051ad`
- `KERNEL32!GetCurrentThreadId` at `0x180005200`
- `KERNEL32!GetCurrentThreadId` at `0x1800051ad`
- `KERNEL32!GetCurrentThreadId` at `0x180005200`
- `KERNEL32!LeaveCriticalSection` at `0x18000508a`
- `KERNEL32!LeaveCriticalSection` at `0x180005190`
- `KERNEL32!LeaveCriticalSection` at `0x180005226`
- `KERNEL32!LeaveCriticalSection` at `0x1800052ec`
- `KERNEL32!LeaveCriticalSection` at `0x180005324`
- `KERNEL32!LeaveCriticalSection` at `0x18000508a`
- `KERNEL32!LeaveCriticalSection` at `0x180005190`
- `KERNEL32!LeaveCriticalSection` at `0x180005226`
- `KERNEL32!LeaveCriticalSection` at `0x1800052ec`
- `KERNEL32!LeaveCriticalSection` at `0x180005324`
- `KERNEL32!EnterCriticalSection` at `0x180005048`
- `KERNEL32!EnterCriticalSection` at `0x1800050b3`
- `KERNEL32!EnterCriticalSection` at `0x1800050da`
- `KERNEL32!EnterCriticalSection` at `0x18000519d`
- `KERNEL32!EnterCriticalSection` at `0x180005240`
- `KERNEL32!EnterCriticalSection` at `0x180005048`
- `KERNEL32!EnterCriticalSection` at `0x1800050b3`
- `KERNEL32!EnterCriticalSection` at `0x1800050da`
- `KERNEL32!EnterCriticalSection` at `0x18000519d`
- `KERNEL32!EnterCriticalSection` at `0x180005240`

## pseudocode

```c
__int64 __fastcall DestroytLineApp(unsigned int a1, unsigned __int64 a2)
{
  __int64 v4; // rcx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rbx
  __int64 v8; // rbp
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  size_t v14; // rdx
  __int64 v15; // rcx
  size_t v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rdi
  __int64 v19; // rcx
  BOOL v20; // edx
  __int64 v21; // rcx
  __int64 HighestPriorityRequestRecipient; // rax
  _QWORD *v23; // rcx
  _QWORD *v24; // rbx
  __int64 v26; // rcx
  _OWORD v27[4]; // [rsp+38h] [rbp-60h] BYREF

  TRACELogPrint(524290, "DestroytLineApp: enter, hLineApp=x%x, ptClient=x%x", a1, a2);
  v5 = ReferenceObject(v4, a1, 1347436876);
  v6 = v5;
  if ( !v5 )
    return dword_180051918 != 0 ? -2147483628 : -2147483568;
  v7 = v5 >> 4;
  EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v5 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  if ( *(_DWORD *)v6 != 1347436876 || a2 != *(_QWORD *)(v6 + 8) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v7 & gdwPointerToLockTableIndexBits));
    DereferenceObject(v26, a1, 1);
    return dword_180051918 != 0 ? -2147483628 : -2147483568;
  }
  *(_DWORD *)v6 = 1280724553;
  while ( 1 )
  {
    v8 = *(_QWORD *)(v6 + 16);
    if ( v8 )
      LODWORD(v8) = *(_DWORD *)(v8 + 24);
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v7 & gdwPointerToLockTableIndexBits));
    if ( !(_DWORD)v8 )
      break;
    DestroytLineClient((unsigned int)v8);
    EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v7 & gdwPointerToLockTableIndexBits));
  }
  EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a2 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  v9 = *(_QWORD *)(v6 + 40);
  if ( v9 )
    *(_QWORD *)(v9 + 32) = *(_QWORD *)(v6 + 32);
  v10 = *(_QWORD *)(v6 + 32);
  v11 = *(_QWORD *)(v6 + 40);
  if ( v10 )
    *(_QWORD *)(v10 + 40) = v11;
  else
    *(_QWORD *)(a2 + 168) = v11;
  v12 = *(_QWORD *)(a2 + 192);
  if ( v12 && !*(_QWORD *)(a2 + 168) )
  {
    memset(v27, 0, 60);
    do
    {
      v13 = *(_QWORD *)(v12 + 80);
      LODWORD(v27[0]) = 0;
      DWORD2(v27[0]) = *(_DWORD *)(v12 + 88);
      HIDWORD(v27[0]) = -2147483576;
      FreeDialogInstance(a2, v27, 60);
      v12 = v13;
    }
    while ( v13 );
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a2 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 7410;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v14, "i\\server\\line.c");
  if ( !--dword_180051918 && !dword_180051928 && (dword_180051900 & 2) == 0 )
  {
    ServerShutdown(v15);
    gbServerInited = 0;
  }
  dword_1800519F8 = 7425;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v16, "i\\server\\line.c");
  LeaveCriticalSection(&CriticalSection);
  v18 = *(_QWORD **)(v6 + 56);
  if ( v18 )
  {
    EnterCriticalSection(&gPriorityListCritSec);
    v19 = v18[3];
    v20 = qword_180051940 == (_QWORD)v18;
    if ( v19 )
      *(_QWORD *)(v19 + 16) = v18[2];
    v21 = v18[2];
    if ( v21 )
      *(_QWORD *)(v21 + 24) = v18[3];
    else
      qword_180051938 = v18[3];
    if ( v20 )
    {
      HighestPriorityRequestRecipient = GetHighestPriorityRequestRecipient(v21);
      v23 = lpMem;
      qword_180051940 = HighestPriorityRequestRecipient;
      if ( lpMem )
      {
        if ( HighestPriorityRequestRecipient )
        {
          NotifyHighestPriorityRequestRecipient(lpMem);
        }
        else
        {
          qword_180051950 = 0;
          lpMem = 0;
          if ( v23 )
          {
            do
            {
              v24 = (_QWORD *)v23[60];
              ServerFree(v23);
              v23 = v24;
            }
            while ( v24 );
          }
          TRACELogPrint(262146, "DestroytLineApp: deleting pending MakeCall requests");
        }
      }
    }
    LeaveCriticalSection(&gPriorityListCritSec);
    ServerFree(v18);
  }
  DereferenceObject(v17, a1, 2);
  return 0;
}

```

## disassembly

```asm
0x180004fcc  mov     [rsp+arg_10], rbx
0x180004fd1  mov     [rsp+arg_18], rbp
0x180004fd6  push    rsi
0x180004fd7  push    rdi
0x180004fd8  push    r14
0x180004fda  sub     rsp, 80h
0x180004fe1  mov     rax, cs:__security_cookie
0x180004fe8  xor     rax, rsp
0x180004feb  mov     [rsp+98h+var_20], rax
0x180004ff0  mov     rsi, rdx
0x180004ff3  mov     r14d, ecx
0x180004ff6  mov     r9, rdx
0x180004ff9  mov     r8d, ecx
0x180004ffc  lea     rdx, aDestroytlineap; "DestroytLineApp: enter, hLineApp=x%x, p"...
0x180005003  mov     ecx, 80002h
0x180005008  call    TRACELogPrint
0x18000500d  mov     ebp, 5050414Ch
0x180005012  mov     edx, r14d
0x180005015  mov     r8d, ebp
0x180005018  call    ReferenceObject
0x18000501d  mov     rdi, rax
0x180005020  test    rax, rax
0x180005023  jz      loc_180005338
0x180005029  mov     rbx, rax
0x18000502c  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180005032  shr     rbx, 4
0x180005036  and     rax, rbx
0x180005039  lea     rcx, [rax+rax*4]
0x18000503d  mov     rax, cs:gLockTable
0x180005044  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180005048  call    cs:__imp_EnterCriticalSection
0x18000504e  cmp     [rdi], ebp
0x180005050  jnz     loc_18000530C
0x180005056  cmp     rsi, [rdi+8]
0x18000505a  jnz     loc_18000530C
0x180005060  mov     dword ptr [rdi], 4C564E49h
0x180005066  mov     rbp, [rdi+10h]
0x18000506a  test    rbp, rbp
0x18000506d  jz      short loc_180005072
0x18000506f  mov     ebp, [rbp+18h]
0x180005072  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180005078  and     rax, rbx
0x18000507b  lea     rdx, [rax+rax*4]
0x18000507f  mov     rax, cs:gLockTable
0x180005086  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x18000508a  call    cs:__imp_LeaveCriticalSection
0x180005090  test    ebp, ebp
0x180005092  jz      short loc_1800050BB
0x180005094  mov     ecx, ebp
0x180005096  call    DestroytLineClient
0x18000509b  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800050a1  and     rax, rbx
0x1800050a4  lea     rcx, [rax+rax*4]
0x1800050a8  mov     rax, cs:gLockTable
0x1800050af  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800050b3  call    cs:__imp_EnterCriticalSection
0x1800050b9  jmp     short loc_180005066
0x1800050bb  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800050c1  mov     rbp, rsi
0x1800050c4  shr     rbp, 4
0x1800050c8  and     rax, rbp
0x1800050cb  lea     rcx, [rax+rax*4]
0x1800050cf  mov     rax, cs:gLockTable
0x1800050d6  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800050da  call    cs:__imp_EnterCriticalSection
0x1800050e0  mov     rcx, [rdi+28h]
0x1800050e4  test    rcx, rcx
0x1800050e7  jz      short loc_1800050F1
0x1800050e9  mov     rax, [rdi+20h]
0x1800050ed  mov     [rcx+20h], rax
0x1800050f1  mov     rax, [rdi+20h]
0x1800050f5  mov     rcx, [rdi+28h]
0x1800050f9  test    rax, rax
0x1800050fc  jz      short loc_180005104
0x1800050fe  mov     [rax+28h], rcx
0x180005102  jmp     short loc_18000510B
0x180005104  mov     [rsi+0A8h], rcx
0x18000510b  mov     rax, [rsi+0C0h]
0x180005112  test    rax, rax
0x180005115  jz      short loc_180005178
0x180005117  cmp     qword ptr [rsi+0A8h], 0
0x18000511f  jnz     short loc_180005178
0x180005121  xorps   xmm0, xmm0
0x180005124  movups  xmmword ptr [rsp+98h+var_40], xmm0
0x180005129  movups  xmmword ptr [rsp+98h+var_40+0Ch], xmm0
0x18000512e  movups  [rsp+98h+var_60], xmm0
0x180005133  movups  [rsp+98h+var_50], xmm0
0x180005138  mov     rbx, [rax+50h]
0x18000513c  lea     rdx, [rsp+98h+var_60]
0x180005141  xor     r9d, r9d
0x180005144  mov     dword ptr [rsp+98h+var_60], 0
0x18000514c  mov     eax, [rax+58h]
0x18000514f  mov     rcx, rsi
0x180005152  mov     dword ptr [rsp+98h+var_60+8], eax
0x180005156  mov     dword ptr [rsp+98h+var_60+0Ch], 80000048h
0x18000515e  lea     r8d, [r9+3Ch]
0x180005162  mov     [rsp+98h+var_78], 0
0x18000516b  call    FreeDialogInstance
0x180005170  mov     rax, rbx
0x180005173  test    rbx, rbx
0x180005176  jnz     short loc_180005138
0x180005178  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18000517e  and     rax, rbp
0x180005181  lea     rcx, [rax+rax*4]
0x180005185  mov     rax, cs:gLockTable
0x18000518c  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180005190  call    cs:__imp_LeaveCriticalSection
0x180005196  lea     rcx, CriticalSection; lpCriticalSection
0x18000519d  call    cs:__imp_EnterCriticalSection
0x1800051a3  mov     cs:dword_1800519E0, 1CF2h
0x1800051ad  call    cs:__imp_GetCurrentThreadId
0x1800051b3  lea     r8, aPrintscanTapiS_4+0Dh; pszSrc
0x1800051ba  mov     cs:dword_1800519E4, eax
0x1800051c0  lea     rcx, pszDest; pszDest
0x1800051c7  call    StringCbCopyA
0x1800051cc  add     cs:dword_180051918, 0FFFFFFFFh
0x1800051d3  jnz     short loc_1800051F6
0x1800051d5  cmp     cs:dword_180051928, 0
0x1800051dc  jnz     short loc_1800051F6
0x1800051de  test    byte ptr cs:dword_180051900, 2
0x1800051e5  jnz     short loc_1800051F6
0x1800051e7  call    ServerShutdown
0x1800051ec  mov     cs:gbServerInited, 0
0x1800051f6  mov     cs:dword_1800519F8, 1D01h
0x180005200  call    cs:__imp_GetCurrentThreadId
0x180005206  lea     r8, aPrintscanTapiS_4+0Dh; pszSrc
0x18000520d  mov     cs:dword_1800519FC, eax
0x180005213  lea     rcx, byte_1800519E8; pszDest
0x18000521a  call    StringCbCopyA
0x18000521f  lea     rcx, CriticalSection; lpCriticalSection
0x180005226  call    cs:__imp_LeaveCriticalSection
0x18000522c  mov     rdi, [rdi+38h]
0x180005230  test    rdi, rdi
0x180005233  jz      loc_1800052FA
0x180005239  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x180005240  call    cs:__imp_EnterCriticalSection
0x180005246  mov     rcx, [rdi+18h]
0x18000524a  xor     edx, edx
0x18000524c  cmp     cs:qword_180051940, rdi
0x180005253  setz    dl
0x180005256  test    rcx, rcx
0x180005259  jz      short loc_180005263
0x18000525b  mov     rax, [rdi+10h]
0x18000525f  mov     [rcx+10h], rax
0x180005263  mov     rcx, [rdi+10h]
0x180005267  mov     rax, [rdi+18h]
0x18000526b  test    rcx, rcx
0x18000526e  jz      short loc_180005276
0x180005270  mov     [rcx+18h], rax
0x180005274  jmp     short loc_18000527D
0x180005276  mov     cs:qword_180051938, rax
0x18000527d  test    edx, edx
0x18000527f  jz      short loc_1800052E5
0x180005281  call    GetHighestPriorityRequestRecipient
0x180005286  mov     rcx, cs:lpMem; lpMem
0x18000528d  mov     cs:qword_180051940, rax
0x180005294  test    rcx, rcx
0x180005297  jz      short loc_1800052E5
0x180005299  test    rax, rax
0x18000529c  jz      short loc_1800052A5
0x18000529e  call    NotifyHighestPriorityRequestRecipient
0x1800052a3  jmp     short loc_1800052E5
0x1800052a5  mov     cs:qword_180051950, 0
0x1800052b0  mov     cs:lpMem, 0
0x1800052bb  test    rcx, rcx
0x1800052be  jz      short loc_1800052D4
0x1800052c0  mov     rbx, [rcx+1E0h]
0x1800052c7  call    ServerFree
0x1800052cc  mov     rcx, rbx
0x1800052cf  test    rbx, rbx
0x1800052d2  jnz     short loc_1800052C0
0x1800052d4  lea     rdx, aDestroytlineap_0; "DestroytLineApp: deleting pending MakeC"...
0x1800052db  mov     ecx, 40002h
0x1800052e0  call    TRACELogPrint
0x1800052e5  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x1800052ec  call    cs:__imp_LeaveCriticalSection
0x1800052f2  mov     rcx, rdi; lpMem
0x1800052f5  call    ServerFree
0x1800052fa  mov     r8d, 2
0x180005300  mov     edx, r14d
0x180005303  call    DereferenceObject
0x180005308  xor     eax, eax
0x18000530a  jmp     short loc_18000534A
0x18000530c  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180005312  and     rax, rbx
0x180005315  lea     rcx, [rax+rax*4]
0x180005319  mov     rax, cs:gLockTable
0x180005320  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180005324  call    cs:__imp_LeaveCriticalSection
0x18000532a  mov     r8d, 1
0x180005330  mov     edx, r14d
0x180005333  call    DereferenceObject
0x180005338  mov     eax, cs:dword_180051918
0x18000533e  neg     eax
0x180005340  sbb     eax, eax
0x180005342  and     eax, 0FFFFFFC4h
0x180005345  add     eax, 80000050h
0x18000534a  mov     rcx, [rsp+98h+var_20]
0x18000534f  xor     rcx, rsp; StackCookie
0x180005352  call    __security_check_cookie
0x180005357  lea     r11, [rsp+98h+var_18]
0x18000535f  mov     rbx, [r11+30h]
0x180005363  mov     rbp, [r11+38h]
0x180005367  mov     rsp, r11
0x18000536a  pop     r14
0x18000536c  pop     rdi
0x18000536d  pop     rsi
0x18000536e  retn
```
