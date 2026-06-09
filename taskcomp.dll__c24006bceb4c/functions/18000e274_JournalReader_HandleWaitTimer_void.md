# JournalReader::HandleWaitTimer(void)

- ea: `0x18000e274`
- end: `0x18000e4d2`
- name: `?HandleWaitTimer@JournalReader@@QEAAJXZ`
- size: `606`
- prototype: `__int64 __fastcall(JournalReader *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180011880`

## callees

- `0x180002b90`
- `0x1800064bc`
- `0x18000c760`
- `0x18000e274`
- `0x18000f5a8`
- `0x18000fbb8`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18000e2d6`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18000e2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2f8`

## pseudocode

```c
__int64 __fastcall JournalReader::HandleWaitTimer(JournalReader *this)
{
  int v2; // esi
  _QWORD *v3; // rcx
  DWORD LastError; // eax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  _QWORD *v7; // r9
  _QWORD *v8; // rdx
  _QWORD *v9; // r8
  __int64 *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  int v14; // r8d
  char *v15; // r9
  int *v17; // [rsp+28h] [rbp-40h]
  char v18[32]; // [rsp+0h] [rbp-68h] BYREF
  int v19; // [rsp+78h] [rbp+10h] BYREF
  int v20; // [rsp+80h] [rbp+18h]
  char v21; // [rsp+88h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_880a4eb608c037d792798d7e53d23858_Traceguids);
  }
  v19 = 0;
  v2 = 0;
  v20 = 0;
  *((_BYTE *)this + 80) = 0;
  if ( CancelWaitableTimer(*((HANDLE *)this + 9)) )
    goto LABEL_10;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, LastError);
LABEL_10:
    v3 = WPP_GLOBAL_Control;
  }
  while ( 1 )
  {
    v5 = (_QWORD *)*((_QWORD *)this + 17);
    v6 = (_QWORD *)*v5;
    if ( (_QWORD *)*v5 == v5 )
      break;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 && *((_BYTE *)v3 + 25) >= 4u )
    {
      v7 = v6 + 4;
      if ( v6[7] >= 8u )
        v7 = (_QWORD *)*v7;
      WPP_SF_SD(
        v3[2],
        38,
        (unsigned int)WPP_880a4eb608c037d792798d7e53d23858_Traceguids,
        (_DWORD)v7,
        *((_DWORD *)v6 + 16));
    }
    try
    {
      if ( (v6[8] & 0x200) != 0 )
      {
        if ( *(_QWORD *)this )
        {
          v8 = v6 + 4;
          if ( v6[7] >= 8u )
            v8 = (_QWORD *)*v8;
          (*(void (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)this + 24LL))(*(_QWORD *)this, v8);
        }
      }
      else
      {
        if ( (v6[8] & 0x1000) != 0 && *(_QWORD *)this )
        {
          v9 = v6 + 4;
          if ( v6[7] >= 8u )
            v9 = (_QWORD *)*v9;
          v10 = (__int64 *)v6[9];
          if ( v10 )
            v11 = *v10;
          else
            v11 = 0;
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD *))(**(_QWORD **)this + 16LL))(*(_QWORD *)this, v11, v9);
        }
        if ( (v6[8] & 0x800) != 0 && *(_QWORD *)this )
        {
          v12 = v6 + 4;
          if ( v6[7] >= 8u )
            v12 = (_QWORD *)*v12;
          (*(void (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, v12);
        }
        if ( (v6[8] & 1) != 0 && *(_QWORD *)this )
        {
          v13 = v6 + 4;
          if ( v6[7] >= 8u )
            v13 = (_QWORD *)*v13;
          (***(void (__fastcall ****)(_QWORD, _QWORD *))this)(*(_QWORD *)this, v13);
        }
      }
      std::_Tree<std::_Tmap_traits<std::wstring,JournalReader::ChangeData,JournalReader::wstringless,t_allocator<std::pair<std::wstring const,JournalReader::ChangeData>>,0>>::erase(
        (char *)this + 136,
        &v21,
        v6);
      v2 = 1;
      v20 = 1;
      v3 = WPP_GLOBAL_Control;
    }
    catch ( ... )
    {
      tsched::KnownExceptionToHResult((tsched *)v3, v18, v14, v15, (unsigned __int8)&v19, v17);
    }
  }
  if ( !v2 && v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 && *((_BYTE *)v3 + 25) >= 4u )
    WPP_SF_(v3[2], 39, WPP_880a4eb608c037d792798d7e53d23858_Traceguids);
  if ( *((_DWORD *)this + 32) )
    JournalReader::_ReadUsnJournal(this, 1);
  return 0;
}

```

## disassembly

```asm
0x18000e274  mov     [rsp+arg_0], rcx
0x18000e279  push    rbx
0x18000e27a  push    rsi
0x18000e27b  push    rdi
0x18000e27c  push    r12
0x18000e27e  push    r14
0x18000e280  push    r15
0x18000e282  sub     rsp, 38h
0x18000e286  mov     rdi, rcx
0x18000e289  lea     r14, WPP_GLOBAL_Control
0x18000e290  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e297  cmp     rcx, r14
0x18000e29a  jz      short loc_18000E2BD
0x18000e29c  test    byte ptr [rcx+1Ch], 2
0x18000e2a0  jz      short loc_18000E2BD
0x18000e2a2  cmp     byte ptr [rcx+19h], 4
0x18000e2a6  jb      short loc_18000E2BD
0x18000e2a8  mov     edx, 24h ; '$'
0x18000e2ad  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000e2b4  mov     rcx, [rcx+10h]
0x18000e2b8  call    WPP_SF_
0x18000e2bd  xor     r15d, r15d
0x18000e2c0  mov     [rsp+68h+arg_8], r15d
0x18000e2c5  xor     esi, esi
0x18000e2c7  mov     [rsp+68h+arg_10], esi
0x18000e2ce  mov     [rdi+50h], sil
0x18000e2d2  mov     rcx, [rdi+48h]; hTimer
0x18000e2d6  call    cs:__imp_CancelWaitableTimer
0x18000e2dc  test    eax, eax
0x18000e2de  jnz     short loc_18000E31B
0x18000e2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2e7  cmp     rcx, r14
0x18000e2ea  jz      short loc_18000E322
0x18000e2ec  test    byte ptr [rcx+1Ch], 2
0x18000e2f0  jz      short loc_18000E322
0x18000e2f2  cmp     byte ptr [rcx+19h], 2
0x18000e2f6  jb      short loc_18000E322
0x18000e2f8  call    cs:__imp_GetLastError
0x18000e2fe  lea     edx, [rsi+25h]
0x18000e301  mov     r9d, eax
0x18000e304  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000e30b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e312  mov     rcx, [rcx+10h]
0x18000e316  call    WPP_SF_d
0x18000e31b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e322  lea     r12, [rdi+88h]
0x18000e329  mov     rax, [r12]
0x18000e32d  mov     rbx, [rax]
0x18000e330  cmp     rbx, rax
0x18000e333  jnz     short loc_18000E33A
0x18000e335  jmp     loc_18000E483
0x18000e33a  cmp     rcx, r14
0x18000e33d  jz      short loc_18000E375
0x18000e33f  test    byte ptr [rcx+1Ch], 2
0x18000e343  jz      short loc_18000E375
0x18000e345  cmp     byte ptr [rcx+19h], 4
0x18000e349  jb      short loc_18000E375
0x18000e34b  mov     eax, [rbx+40h]
0x18000e34e  lea     r9, [rbx+20h]
0x18000e352  cmp     qword ptr [rbx+38h], 8
0x18000e357  jb      short loc_18000E35C
0x18000e359  mov     r9, [r9]
0x18000e35c  mov     edx, 26h ; '&'
0x18000e361  mov     [rsp+68h+var_48], eax
0x18000e365  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000e36c  mov     rcx, [rcx+10h]
0x18000e370  call    WPP_SF_SD
0x18000e375  test    dword ptr [rbx+40h], 200h
0x18000e37c  jz      short loc_18000E3A9
0x18000e37e  mov     rcx, [rdi]
0x18000e381  test    rcx, rcx
0x18000e384  jz      loc_18000E439
0x18000e38a  mov     rax, [rcx]
0x18000e38d  lea     rdx, [rbx+20h]
0x18000e391  cmp     qword ptr [rbx+38h], 8
0x18000e396  jb      short loc_18000E39B
0x18000e398  mov     rdx, [rdx]
0x18000e39b  mov     rax, [rax+18h]
0x18000e39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3a4  jmp     loc_18000E439
0x18000e3a9  test    dword ptr [rbx+40h], 1000h
0x18000e3b0  jz      short loc_18000E3E7
0x18000e3b2  mov     rcx, [rdi]
0x18000e3b5  test    rcx, rcx
0x18000e3b8  jz      short loc_18000E3E7
0x18000e3ba  mov     rax, [rcx]
0x18000e3bd  mov     r9, [rax+10h]
0x18000e3c1  lea     r8, [rbx+20h]
0x18000e3c5  cmp     qword ptr [rbx+38h], 8
0x18000e3ca  jb      short loc_18000E3CF
0x18000e3cc  mov     r8, [r8]
0x18000e3cf  mov     rax, [rbx+48h]
0x18000e3d3  test    rax, rax
0x18000e3d6  jz      short loc_18000E3DD
0x18000e3d8  mov     rdx, [rax]
0x18000e3db  jmp     short loc_18000E3DF
0x18000e3dd  xor     edx, edx
0x18000e3df  mov     rax, r9
0x18000e3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3e7  test    dword ptr [rbx+40h], 800h
0x18000e3ee  jz      short loc_18000E412
0x18000e3f0  mov     rcx, [rdi]
0x18000e3f3  test    rcx, rcx
0x18000e3f6  jz      short loc_18000E412
0x18000e3f8  mov     rax, [rcx]
0x18000e3fb  lea     rdx, [rbx+20h]
0x18000e3ff  cmp     qword ptr [rbx+38h], 8
0x18000e404  jb      short loc_18000E409
0x18000e406  mov     rdx, [rdx]
0x18000e409  mov     rax, [rax+8]
0x18000e40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e412  test    byte ptr [rbx+40h], 1
0x18000e416  jz      short loc_18000E439
0x18000e418  mov     rcx, [rdi]
0x18000e41b  test    rcx, rcx
0x18000e41e  jz      short loc_18000E439
0x18000e420  mov     rax, [rcx]
0x18000e423  lea     rdx, [rbx+20h]
0x18000e427  cmp     qword ptr [rbx+38h], 8
0x18000e42c  jb      short loc_18000E431
0x18000e42e  mov     rdx, [rdx]
0x18000e431  mov     rax, [rax]
0x18000e434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e439  mov     r8, rbx
0x18000e43c  lea     rdx, [rsp+68h+arg_18]
0x18000e444  mov     rcx, r12
0x18000e447  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UChangeData@JournalReader@@Uwstringless@4@V?$t_allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UChangeData@JournalReader@@@std@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UChangeData@JournalReader@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UChangeData@JournalReader@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,JournalReader::ChangeData,JournalReader::wstringless,t_allocator<std::pair<std::wstring const,JournalReader::ChangeData>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,JournalReader::ChangeData>>>>)
0x18000e44c  mov     esi, 1
0x18000e451  mov     [rsp+68h+arg_10], esi
0x18000e458  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e45f  jmp     loc_18000E322
0x18000e464  lea     r14, WPP_GLOBAL_Control
0x18000e46b  mov     rdi, [rsp+68h+arg_0]
0x18000e470  mov     r15d, [rsp+68h+arg_8]
0x18000e475  mov     esi, [rsp+68h+arg_10]
0x18000e47c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e483  test    esi, esi
0x18000e485  jnz     short loc_18000E4AB
0x18000e487  cmp     rcx, r14
0x18000e48a  jz      short loc_18000E4AB
0x18000e48c  test    byte ptr [rcx+1Ch], 2
0x18000e490  jz      short loc_18000E4AB
0x18000e492  cmp     byte ptr [rcx+19h], 4
0x18000e496  jb      short loc_18000E4AB
0x18000e498  lea     edx, [rsi+27h]
0x18000e49b  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000e4a2  mov     rcx, [rcx+10h]
0x18000e4a6  call    WPP_SF_
0x18000e4ab  cmp     dword ptr [rdi+80h], 0
0x18000e4b2  jz      short loc_18000E4C1
0x18000e4b4  mov     edx, 1; int
0x18000e4b9  mov     rcx, rdi; this
0x18000e4bc  call    ?_ReadUsnJournal@JournalReader@@AEAAJH@Z; JournalReader::_ReadUsnJournal(int)
0x18000e4c1  mov     eax, r15d
0x18000e4c4  add     rsp, 38h
0x18000e4c8  pop     r15
0x18000e4ca  pop     r14
0x18000e4cc  pop     r12
0x18000e4ce  pop     rdi
0x18000e4cf  pop     rsi
0x18000e4d0  pop     rbx
0x18000e4d1  retn
```
