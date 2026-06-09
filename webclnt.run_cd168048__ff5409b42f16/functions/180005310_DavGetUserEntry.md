# DavGetUserEntry

- ea: `0x180005310`
- end: `0x180005560`
- name: `DavGetUserEntry`
- size: `592`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000235c`
- `0x180002ca0`
- `0x180005a38`
- `0x180006670`
- `0x180006a90`
- `0x180007b50`
- `0x180009480`
- `0x18000a370`

## callees

- `0x180005310`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b89c`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180005544`
- `ntdll!RtlCopyLuid` at `0x180005544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000545a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000545a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054ec`
- `KERNEL32!LocalLock` at `0x180005466`
- `KERNEL32!LocalLock` at `0x180005493`
- `KERNEL32!LocalLock` at `0x180005466`
- `KERNEL32!LocalLock` at `0x180005493`
- `KERNEL32!LocalAlloc` at `0x1800054dd`
- `KERNEL32!LocalAlloc` at `0x1800054dd`
- `KERNEL32!LocalReAlloc` at `0x18000544f`
- `KERNEL32!LocalReAlloc` at `0x18000544f`
- `KERNEL32!LocalUnlock` at `0x1800053fa`
- `KERNEL32!LocalUnlock` at `0x1800053fa`

## pseudocode

```c
__int64 __fastcall DavGetUserEntry(LPVOID *a1, struct _LUID *a2, unsigned int *a3, int a4)
{
  unsigned int v4; // ebp
  unsigned int v8; // ebx
  _QWORD *v9; // r8
  DWORD LowPart; // edx
  _QWORD *v12; // rcx
  DWORD v13; // ebx
  int v14; // eax
  unsigned int v15; // esi
  DWORD LastError; // eax
  HLOCAL v17; // rax
  __int64 v18; // rdx
  LPVOID v19; // rax
  __int64 v20; // r9
  DWORD v21; // eax

  v4 = 0;
  v8 = -1;
  if ( *((_DWORD *)a1 + 28) )
  {
    v9 = *a1;
    LowPart = a2->LowPart;
    while ( LowPart != LODWORD(v9[2 * v4 + 1]) || a2->HighPart != HIDWORD(v9[2 * v4 + 1]) )
    {
      if ( v8 == -1 && !v9[2 * v4] )
        v8 = v4;
      if ( ++v4 >= *((_DWORD *)a1 + 28) )
        goto LABEL_9;
    }
    *a3 = v4;
    return 0;
  }
LABEL_9:
  if ( !a4 )
    return 2221;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      239,
      WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
      a2->LowPart,
      a2->HighPart);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v8 != -1 )
    goto LABEL_44;
  v13 = 0;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
    WPP_SF_(v12[2], 241, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
  v14 = *((_DWORD *)a1 + 28);
  v15 = 16 * (v14 + 3);
  if ( v14 )
  {
    if ( !LocalUnlock(a1[13]) )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
        return v13;
      }
    }
    v17 = LocalReAlloc(a1[13], v15, 0x42u);
    if ( !v17 )
    {
      v13 = GetLastError();
      *a1 = LocalLock(a1[13]);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v18 = 243;
      goto LABEL_34;
    }
    a1[13] = v17;
  }
  else
  {
    v17 = LocalAlloc(0x42u, v15);
    a1[13] = v17;
    if ( !v17 )
    {
      v21 = GetLastError();
      v13 = v21;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v18 = 244;
      v20 = v21;
      goto LABEL_35;
    }
  }
  *((_DWORD *)a1 + 28) += 3;
  v19 = LocalLock(v17);
  *a1 = v19;
  if ( !v19 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v18 = 245;
LABEL_34:
    v20 = v13;
LABEL_35:
    WPP_SF_d(v12[2], v18, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v20);
  }
  v12 = WPP_GLOBAL_Control;
LABEL_37:
  if ( v13 )
    return v13;
  v8 = v4;
LABEL_44:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
    WPP_SF_d(v12[2], 240, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v8);
  RtlCopyLuid((PLUID)*a1 + 2 * v8 + 1, a2);
  *a3 = v8;
  return 0;
}

```

## disassembly

```asm
0x180005310  push    rbx
0x180005312  push    rbp
0x180005313  push    rsi
0x180005314  push    rdi
0x180005315  push    r12
0x180005317  push    r13
0x180005319  push    r14
0x18000531b  push    r15
0x18000531d  sub     rsp, 38h
0x180005321  or      esi, 0FFFFFFFFh
0x180005324  xor     ebp, ebp
0x180005326  mov     r15, r8
0x180005329  mov     r14, rdx
0x18000532c  mov     rdi, rcx
0x18000532f  mov     ebx, esi
0x180005331  cmp     [rcx+70h], ebp
0x180005334  jbe     short loc_180005365
0x180005336  mov     r8, [rcx]
0x180005339  mov     edx, [rdx]
0x18000533b  mov     ecx, ebp
0x18000533d  add     rcx, rcx
0x180005340  cmp     edx, [r8+rcx*8+8]
0x180005345  jnz     short loc_180005352
0x180005347  mov     eax, [r8+rcx*8+0Ch]
0x18000534c  cmp     [r14+4], eax
0x180005350  jz      short loc_180005374
0x180005352  cmp     ebx, esi
0x180005354  jnz     short loc_18000535E
0x180005356  cmp     qword ptr [r8+rcx*8], 0
0x18000535b  cmovz   ebx, ebp
0x18000535e  inc     ebp
0x180005360  cmp     ebp, [rdi+70h]
0x180005363  jb      short loc_18000533B
0x180005365  test    r9d, r9d
0x180005368  jnz     short loc_18000537C
0x18000536a  mov     eax, 8ADh
0x18000536f  jmp     loc_18000554F
0x180005374  mov     [r15], ebp
0x180005377  jmp     loc_18000554D
0x18000537c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005383  lea     r12, WPP_GLOBAL_Control
0x18000538a  lea     r13, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180005391  cmp     rcx, r12
0x180005394  jz      short loc_1800053BF
0x180005396  test    byte ptr [rcx+1Ch], 2
0x18000539a  jz      short loc_1800053BF
0x18000539c  mov     eax, [r14+4]
0x1800053a0  mov     edx, 0EFh
0x1800053a5  mov     r9d, [r14]
0x1800053a8  mov     r8, r13
0x1800053ab  mov     rcx, [rcx+10h]
0x1800053af  mov     [rsp+78h+var_58], eax
0x1800053b3  call    WPP_SF_Dd
0x1800053b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053bf  cmp     ebx, esi
0x1800053c1  jnz     loc_180005512
0x1800053c7  xor     ebx, ebx
0x1800053c9  cmp     rcx, r12
0x1800053cc  jz      short loc_1800053E5
0x1800053ce  test    byte ptr [rcx+1Ch], 2
0x1800053d2  jz      short loc_1800053E5
0x1800053d4  mov     rcx, [rcx+10h]
0x1800053d8  mov     edx, 0F1h
0x1800053dd  mov     r8, r13
0x1800053e0  call    WPP_SF_
0x1800053e5  mov     eax, [rdi+70h]
0x1800053e8  lea     esi, [rax+3]
0x1800053eb  shl     esi, 4
0x1800053ee  test    eax, eax
0x1800053f0  jz      loc_1800054D6
0x1800053f6  mov     rcx, [rdi+68h]; hMem
0x1800053fa  call    cs:__imp_LocalUnlock
0x180005400  test    eax, eax
0x180005402  jnz     short loc_180005443
0x180005404  call    cs:__imp_GetLastError
0x18000540a  mov     ebx, eax
0x18000540c  test    eax, eax
0x18000540e  jz      short loc_180005443
0x180005410  mov     rcx, cs:WPP_GLOBAL_Control
0x180005417  cmp     rcx, r12
0x18000541a  jz      loc_1800054D2
0x180005420  test    byte ptr [rcx+1Ch], 1
0x180005424  jz      loc_1800054D2
0x18000542a  mov     rcx, [rcx+10h]
0x18000542e  mov     edx, 0F2h
0x180005433  mov     r9d, eax
0x180005436  mov     r8, r13
0x180005439  call    WPP_SF_d
0x18000543e  jmp     loc_1800054D2
0x180005443  mov     rcx, [rdi+68h]; hMem
0x180005447  mov     r8d, 42h ; 'B'; uFlags
0x18000544d  mov     edx, esi; uBytes
0x18000544f  call    cs:__imp_LocalReAlloc
0x180005455  test    rax, rax
0x180005458  jnz     short loc_180005488
0x18000545a  call    cs:__imp_GetLastError
0x180005460  mov     rcx, [rdi+68h]; hMem
0x180005464  mov     ebx, eax
0x180005466  call    cs:__imp_LocalLock
0x18000546c  mov     [rdi], rax
0x18000546f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005476  cmp     rcx, r12
0x180005479  jz      short loc_1800054CE
0x18000547b  test    byte ptr [rcx+1Ch], 1
0x18000547f  jz      short loc_1800054CE
0x180005481  mov     edx, 0F3h
0x180005486  jmp     short loc_1800054B8
0x180005488  mov     [rdi+68h], rax
0x18000548c  add     dword ptr [rdi+70h], 3
0x180005490  mov     rcx, rax; hMem
0x180005493  call    cs:__imp_LocalLock
0x180005499  mov     [rdi], rax
0x18000549c  test    rax, rax
0x18000549f  jnz     short loc_1800054C7
0x1800054a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054a8  cmp     rcx, r12
0x1800054ab  jz      short loc_1800054CE
0x1800054ad  test    byte ptr [rcx+1Ch], 1
0x1800054b1  jz      short loc_1800054CE
0x1800054b3  mov     edx, 0F5h
0x1800054b8  mov     r9d, ebx
0x1800054bb  mov     rcx, [rcx+10h]
0x1800054bf  mov     r8, r13
0x1800054c2  call    WPP_SF_d
0x1800054c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054ce  test    ebx, ebx
0x1800054d0  jz      short loc_180005510
0x1800054d2  mov     eax, ebx
0x1800054d4  jmp     short loc_18000554F
0x1800054d6  mov     edx, esi; uBytes
0x1800054d8  mov     ecx, 42h ; 'B'; uFlags
0x1800054dd  call    cs:__imp_LocalAlloc
0x1800054e3  mov     [rdi+68h], rax
0x1800054e7  test    rax, rax
0x1800054ea  jnz     short loc_18000548C
0x1800054ec  call    cs:__imp_GetLastError
0x1800054f2  mov     ebx, eax
0x1800054f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054fb  cmp     rcx, r12
0x1800054fe  jz      short loc_1800054CE
0x180005500  test    byte ptr [rcx+1Ch], 1
0x180005504  jz      short loc_1800054CE
0x180005506  mov     edx, 0F4h
0x18000550b  mov     r9d, eax
0x18000550e  jmp     short loc_1800054BB
0x180005510  mov     ebx, ebp
0x180005512  cmp     rcx, r12
0x180005515  jz      short loc_180005531
0x180005517  test    byte ptr [rcx+1Ch], 2
0x18000551b  jz      short loc_180005531
0x18000551d  mov     rcx, [rcx+10h]
0x180005521  mov     edx, 0F0h
0x180005526  mov     r9d, ebx
0x180005529  mov     r8, r13
0x18000552c  call    WPP_SF_d
0x180005531  mov     rax, [rdi]
0x180005534  mov     rdx, r14; SourceLuid
0x180005537  add     rax, 8
0x18000553b  mov     ecx, ebx
0x18000553d  shl     rcx, 4
0x180005541  add     rcx, rax; DestinationLuid
0x180005544  call    cs:__imp_RtlCopyLuid
0x18000554a  mov     [r15], ebx
0x18000554d  xor     eax, eax
0x18000554f  add     rsp, 38h
0x180005553  pop     r15
0x180005555  pop     r14
0x180005557  pop     r13
0x180005559  pop     r12
0x18000555b  pop     rdi
0x18000555c  pop     rsi
0x18000555d  pop     rbp
0x18000555e  pop     rbx
0x18000555f  retn
```
