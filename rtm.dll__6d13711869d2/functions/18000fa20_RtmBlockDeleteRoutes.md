# RtmBlockDeleteRoutes

- ea: `0x18000fa20`
- end: `0x18000fc9c`
- name: `RtmBlockDeleteRoutes`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800108f0`

## callees

- `0x18000e4c0`
- `0x18000e7a0`
- `0x18000ecec`
- `0x18000fa20`
- `0x18000ff90`
- `0x180010090`
- `0x18001163c`
- `0x180011800`
- `0x180020010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fa9c`
- `KERNEL32!GetLastError` at `0x18000fa9c`

## pseudocode

```c
DWORD __fastcall RtmBlockDeleteRoutes(__int64 a1, int a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 *v5; // rbx
  __int64 EnumerationHandle; // rax
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 *v10; // r15
  __int64 *i; // r14
  __int64 *j; // r14
  __int64 v13; // r9
  __int64 v14; // r8
  int v15; // edi
  __int64 v16; // rdx
  __int64 v17; // rdx

  v4 = *(_DWORD *)(a1 + 16) ^ 0x52544D00u;
  v5 = &Tables[48 * v4];
  if ( (_DWORD)v4 )
    return 6;
  if ( _InterlockedAdd((volatile signed __int32 *)v5 + 2, 1u) <= 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v5 + 2);
    return 6;
  }
  if ( (a2 & 0xFFFFFFFC) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v5 + 2);
    return 87;
  }
  else
  {
    *(_DWORD *)(a3 + 8) = *(_DWORD *)(a1 + 20);
    EnumerationHandle = RtmCreateEnumerationHandle(v4, a2 | 4u);
    v8 = EnumerationHandle;
    if ( EnumerationHandle )
    {
      if ( DoEnterSyncList((__int64)v5, *(_QWORD *)(EnumerationHandle + 80), 1) )
      {
        while ( 1 )
        {
          v15 = DoEnumerate(v5, v8, 4294967291LL);
          if ( v15 )
            break;
          v9 = *(_QWORD *)(16LL * *(int *)(v8 + 68) + v8) - 16LL * *(int *)(v8 + 68);
          if ( *(_DWORD *)(v8 + 68) )
            LeaveSyncList(v5, *(_QWORD *)(v8 + 80));
          if ( (*(_BYTE *)(v9 + 64) & 2) != 0 )
          {
            v10 = 0;
            for ( i = *(__int64 **)(v9 + 8); i != (__int64 *)(*(_QWORD *)(v9 + 72) + 16LL); i = (__int64 *)i[1] )
            {
              if ( (i[8] & 5) == 4 )
              {
                if ( ((unsigned int (__fastcall *)(__int64, __int64))v5[36])(v9 + 116, (__int64)i + 116) )
                  break;
                if ( !v10 || ((int (__fastcall *)(__int64, __int64))v5[39])((__int64)v10 + 84, (__int64)i + 84) > 0 )
                  v10 = i;
              }
            }
            for ( j = *(__int64 **)v9; j != (__int64 *)(*(_QWORD *)(v9 + 72) + 16LL); j = (__int64 *)*j )
            {
              if ( (j[8] & 5) == 4 )
              {
                if ( ((unsigned int (__fastcall *)(__int64, __int64))v5[36])(v9 + 116, (__int64)j + 116) )
                  break;
                if ( !v10 || ((int (__fastcall *)(__int64, __int64))v5[39])((__int64)v10 + 84, (__int64)j + 84) > 0 )
                  v10 = j;
              }
            }
            if ( v10 )
            {
              *(_DWORD *)(v9 + 64) &= ~2u;
              *((_DWORD *)v10 + 16) |= 2u;
              v13 = (__int64)v10 + 84;
              v14 = 3;
            }
            else
            {
              _InterlockedDecrement((volatile signed __int32 *)v5 + 9);
              v13 = 0;
              v14 = 2;
            }
            NotifyClients(v5, a1, v14, v13, v9 + 84);
          }
          v15 = RemoveRouteNode(v5);
          if ( v15 )
            break;
          if ( *(_DWORD *)(v8 + 68) && !DoEnterSyncList((__int64)v5, *(_QWORD *)(v8 + 80), 1) )
          {
            v15 = 1450;
            v16 = *(_QWORD *)(v8 + 88);
            if ( v16 )
              LeaveSyncList(v5, v16);
            break;
          }
        }
        if ( v15 == 259 )
        {
          v17 = *(_QWORD *)(v8 + 88);
          if ( v17 )
            LeaveSyncList(v5, v17);
          LeaveSyncList(v5, *(_QWORD *)(v8 + 80));
          v15 = 0;
        }
        RtmCloseEnumerationHandle((HGLOBAL)v8);
        _InterlockedDecrement((volatile signed __int32 *)v5 + 2);
        return v15;
      }
      else
      {
        RtmCloseEnumerationHandle((HGLOBAL)v8);
        _InterlockedDecrement((volatile signed __int32 *)v5 + 2);
        return 1450;
      }
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)v5 + 2);
      return GetLastError();
    }
  }
}

```

## disassembly

```asm
0x18000fa20  push    rbx
0x18000fa22  push    rsi
0x18000fa23  push    rdi
0x18000fa24  push    r13
0x18000fa26  push    r14
0x18000fa28  push    r15
0x18000fa2a  sub     rsp, 48h
0x18000fa2e  mov     r13, rcx
0x18000fa31  mov     eax, [rcx+10h]
0x18000fa34  xor     eax, 52544D00h
0x18000fa39  mov     ecx, eax
0x18000fa3b  mov     [rsp+78h+var_48], ecx
0x18000fa3f  lea     rbx, [rax+rax*2]
0x18000fa43  shl     rbx, 7
0x18000fa47  lea     rax, Tables
0x18000fa4e  add     rbx, rax
0x18000fa51  mov     [rsp+78h+var_40], rbx
0x18000fa56  cmp     ecx, 1
0x18000fa59  jnb     loc_18000FC82
0x18000fa5f  lock add dword ptr [rbx+8], 1
0x18000fa64  jle     loc_18000FC7E
0x18000fa6a  test    edx, 0FFFFFFFCh
0x18000fa70  jz      short loc_18000FA80
0x18000fa72  lock dec dword ptr [rbx+8]
0x18000fa76  mov     eax, 57h ; 'W'
0x18000fa7b  jmp     loc_18000FC8E
0x18000fa80  mov     eax, [r13+14h]
0x18000fa84  mov     [r8+8], eax
0x18000fa88  or      edx, 4
0x18000fa8b  call    RtmCreateEnumerationHandle
0x18000fa90  mov     rsi, rax
0x18000fa93  test    rax, rax
0x18000fa96  jnz     short loc_18000FAA7
0x18000fa98  lock dec dword ptr [rbx+8]
0x18000fa9c  call    cs:__imp_GetLastError
0x18000faa2  jmp     loc_18000FC8E
0x18000faa7  mov     r8b, 1
0x18000faaa  mov     rdx, [rax+50h]
0x18000faae  mov     rcx, rbx
0x18000fab1  call    DoEnterSyncList
0x18000fab6  test    al, al
0x18000fab8  jnz     loc_18000FC14
0x18000fabe  mov     rcx, rsi; hMem
0x18000fac1  call    RtmCloseEnumerationHandle
0x18000fac6  lock dec dword ptr [rbx+8]
0x18000faca  mov     eax, 5AAh
0x18000facf  jmp     loc_18000FC8E
0x18000fad4  movsxd  rax, dword ptr [rsi+44h]
0x18000fad8  shl     rax, 4
0x18000fadc  mov     rdi, [rax+rsi]
0x18000fae0  sub     rdi, rax
0x18000fae3  cmp     dword ptr [rsi+44h], 0
0x18000fae7  jz      short loc_18000FAF5
0x18000fae9  mov     rdx, [rsi+50h]
0x18000faed  mov     rcx, rbx
0x18000faf0  call    LeaveSyncList
0x18000faf5  test    byte ptr [rdi+40h], 2
0x18000faf9  jz      loc_18000FBEB
0x18000faff  xor     r15d, r15d
0x18000fb02  mov     r14, [rdi+8]
0x18000fb06  jmp     short loc_18000FB4E
0x18000fb08  mov     eax, [r14+40h]
0x18000fb0c  and     al, 5
0x18000fb0e  cmp     al, 4
0x18000fb10  jnz     short loc_18000FB4A
0x18000fb12  lea     rdx, [r14+74h]
0x18000fb16  lea     rcx, [rdi+74h]
0x18000fb1a  mov     rax, [rbx+120h]
0x18000fb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb26  test    eax, eax
0x18000fb28  jnz     short loc_18000FB5B
0x18000fb2a  test    r15, r15
0x18000fb2d  jz      short loc_18000FB47
0x18000fb2f  lea     rdx, [r14+54h]
0x18000fb33  lea     rcx, [r15+54h]
0x18000fb37  mov     rax, [rbx+138h]
0x18000fb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb43  test    eax, eax
0x18000fb45  jle     short loc_18000FB4A
0x18000fb47  mov     r15, r14
0x18000fb4a  mov     r14, [r14+8]
0x18000fb4e  mov     rax, [rdi+48h]
0x18000fb52  add     rax, 10h
0x18000fb56  cmp     r14, rax
0x18000fb59  jnz     short loc_18000FB08
0x18000fb5b  mov     r14, [rdi]
0x18000fb5e  jmp     short loc_18000FBA5
0x18000fb60  mov     eax, [r14+40h]
0x18000fb64  and     al, 5
0x18000fb66  cmp     al, 4
0x18000fb68  jnz     short loc_18000FBA2
0x18000fb6a  lea     rdx, [r14+74h]
0x18000fb6e  lea     rcx, [rdi+74h]
0x18000fb72  mov     rax, [rbx+120h]
0x18000fb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb7e  test    eax, eax
0x18000fb80  jnz     short loc_18000FBB2
0x18000fb82  test    r15, r15
0x18000fb85  jz      short loc_18000FB9F
0x18000fb87  lea     rdx, [r14+54h]
0x18000fb8b  lea     rcx, [r15+54h]
0x18000fb8f  mov     rax, [rbx+138h]
0x18000fb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb9b  test    eax, eax
0x18000fb9d  jle     short loc_18000FBA2
0x18000fb9f  mov     r15, r14
0x18000fba2  mov     r14, [r14]
0x18000fba5  mov     rax, [rdi+48h]
0x18000fba9  add     rax, 10h
0x18000fbad  cmp     r14, rax
0x18000fbb0  jnz     short loc_18000FB60
0x18000fbb2  lea     rax, [rdi+54h]
0x18000fbb6  mov     [rsp+78h+var_58], rax
0x18000fbbb  mov     rdx, r13
0x18000fbbe  mov     rcx, rbx
0x18000fbc1  test    r15, r15
0x18000fbc4  jz      short loc_18000FBDB
0x18000fbc6  and     dword ptr [rdi+40h], 0FFFFFFFDh
0x18000fbca  or      dword ptr [r15+40h], 2
0x18000fbcf  lea     r9, [r15+54h]
0x18000fbd3  mov     r8d, 3
0x18000fbd9  jmp     short loc_18000FBE6
0x18000fbdb  lock dec dword ptr [rbx+24h]
0x18000fbdf  xor     r9d, r9d
0x18000fbe2  lea     r8d, [r9+2]
0x18000fbe6  call    NotifyClients
0x18000fbeb  mov     rdx, rdi
0x18000fbee  mov     rcx, rbx; Context
0x18000fbf1  call    RemoveRouteNode
0x18000fbf6  mov     edi, eax
0x18000fbf8  test    eax, eax
0x18000fbfa  jnz     short loc_18000FC47
0x18000fbfc  cmp     [rsi+44h], eax
0x18000fbff  jz      short loc_18000FC14
0x18000fc01  mov     r8b, 1
0x18000fc04  mov     rdx, [rsi+50h]
0x18000fc08  mov     rcx, rbx
0x18000fc0b  call    DoEnterSyncList
0x18000fc10  test    al, al
0x18000fc12  jz      short loc_18000FC31
0x18000fc14  mov     r8d, 0FFFFFFFBh
0x18000fc1a  mov     rdx, rsi
0x18000fc1d  mov     rcx, rbx
0x18000fc20  call    DoEnumerate
0x18000fc25  test    eax, eax
0x18000fc27  mov     edi, eax
0x18000fc29  jz      loc_18000FAD4
0x18000fc2f  jmp     short loc_18000FC47
0x18000fc31  mov     edi, 5AAh
0x18000fc36  mov     rdx, [rsi+58h]
0x18000fc3a  test    rdx, rdx
0x18000fc3d  jz      short loc_18000FC47
0x18000fc3f  mov     rcx, rbx
0x18000fc42  call    LeaveSyncList
0x18000fc47  cmp     edi, 103h
0x18000fc4d  jnz     short loc_18000FC6E
0x18000fc4f  mov     rdx, [rsi+58h]
0x18000fc53  test    rdx, rdx
0x18000fc56  jz      short loc_18000FC60
0x18000fc58  mov     rcx, rbx
0x18000fc5b  call    LeaveSyncList
0x18000fc60  mov     rdx, [rsi+50h]
0x18000fc64  mov     rcx, rbx
0x18000fc67  call    LeaveSyncList
0x18000fc6c  xor     edi, edi
0x18000fc6e  mov     rcx, rsi; hMem
0x18000fc71  call    RtmCloseEnumerationHandle
0x18000fc76  lock dec dword ptr [rbx+8]
0x18000fc7a  mov     eax, edi
0x18000fc7c  jmp     short loc_18000FC8E
0x18000fc7e  lock dec dword ptr [rbx+8]
0x18000fc82  mov     eax, 6
0x18000fc87  jmp     short loc_18000FC8E
0x18000fc89  mov     eax, 6
0x18000fc8e  add     rsp, 48h
0x18000fc92  pop     r15
0x18000fc94  pop     r14
0x18000fc96  pop     r13
0x18000fc98  pop     rdi
0x18000fc99  pop     rsi
0x18000fc9a  pop     rbx
0x18000fc9b  retn
0x18001fd1e  push    rbp
0x18001fd20  sub     rsp, 30h
0x18001fd24  mov     rbp, rdx
0x18001fd27  mov     rax, [rcx]
0x18001fd2a  xor     ecx, ecx
0x18001fd2c  cmp     dword ptr [rax], 0C0000005h
0x18001fd32  setz    cl
0x18001fd35  mov     eax, ecx
0x18001fd37  add     rsp, 30h
0x18001fd3b  pop     rbp
0x18001fd3c  retn
```
