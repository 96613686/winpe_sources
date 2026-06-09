# bcpRead(tagDBC *,BCPFILE *,uint,uchar *)

- ea: `0x383976a90`
- end: `0x383976e8e`
- name: `?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z`
- size: `1022`
- prototype: `__int16(struct tagDBC *, struct BCPFILE *, unsigned int, unsigned __int8 *)`
- caller_count: `19`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x383968c50`
- `0x383968ec0`
- `0x38396ae70`
- `0x38396bb70`
- `0x38396dd70`
- `0x3839776b0`
- `0x38397a630`
- `0x38397b320`
- `0x38397ec90`
- `0x38397fd00`
- `0x3839800c0`
- `0x3839801d0`
- `0x3839802b0`
- `0x383980420`
- `0x3839804e0`
- `0x3839811f0`
- `0x383985ce0`
- `0x383985f70`
- `0x383986240`

## callees

- `0x3838427d0`
- `0x38391aed0`
- `0x383976a90`
- `0x383980420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383976b76`
- `KERNEL32!GetLastError` at `0x383976b76`
- `KERNEL32!ReadFile` at `0x383976b25`
- `KERNEL32!ReadFile` at `0x383976b97`
- `KERNEL32!ReadFile` at `0x383976be2`
- `KERNEL32!ReadFile` at `0x383976cf4`
- `KERNEL32!ReadFile` at `0x383976b25`
- `KERNEL32!ReadFile` at `0x383976b97`
- `KERNEL32!ReadFile` at `0x383976be2`
- `KERNEL32!ReadFile` at `0x383976cf4`
- `KERNEL32!SetFilePointer` at `0x383976b6b`
- `KERNEL32!SetFilePointer` at `0x383976b6b`

## pseudocode

```c
__int64 __fastcall bcpRead(struct tagDBC *a1, struct BCPFILE *a2, DWORD a3, unsigned __int8 *a4)
{
  size_t v5; // r14
  unsigned __int16 v8; // di
  unsigned __int64 v9; // rcx
  __int64 v10; // rax
  void *v11; // rdx
  LONG v12; // edx
  DWORD v13; // edx
  __int64 v14; // r15
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // r15
  __int64 v17; // rax
  __int64 v18; // r13
  __int64 v19; // r8
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  LONG DistanceToMoveHigh; // [rsp+30h] [rbp-38h] BYREF
  DWORD v24; // [rsp+34h] [rbp-34h] BYREF
  DWORD v25; // [rsp+38h] [rbp-30h] BYREF
  DWORD v26; // [rsp+3Ch] [rbp-2Ch] BYREF
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+10h] BYREF

  v5 = a3;
  v8 = 0;
  if ( *((_DWORD *)a2 + 16) )
  {
    v9 = *((_QWORD *)a2 + 7);
    if ( a3 + v9 >= v9 && a3 + v9 <= *((_QWORD *)a2 + 4) )
    {
      memcpy(a4, (const void *)(*((_QWORD *)a2 + 2) + v9), a3);
      *((_QWORD *)a2 + 7) += v5;
      goto LABEL_42;
    }
    goto LABEL_41;
  }
  v10 = *((_QWORD *)a1 + 1006);
  v11 = *(void **)(v10 + 1864);
  if ( !v11 )
  {
    if ( ReadFile(*(HANDLE *)a2, a4, a3, &NumberOfBytesRead, 0) && NumberOfBytesRead )
    {
LABEL_42:
      if ( (bidGblFlags & 2) != 0 && (v8 || (bidGblFlags & 0x40) != 0) )
      {
        v21 = 7932929;
        if ( v8 )
          v21 = 7932961;
        bidTraceW(off_383B43238[0], v21, off_383B494E8[0], (unsigned int)(__int16)v8);
      }
      return v8;
    }
    goto LABEL_41;
  }
  if ( a3 >= 0x3800 )
  {
    v12 = *(_DWORD *)(v10 + 1608);
    DistanceToMoveHigh = HIDWORD(*(_QWORD *)(v10 + 1608));
    if ( (SetFilePointer(*(HANDLE *)a2, v12, &DistanceToMoveHigh, 0) != -1 || !GetLastError())
      && ReadFile(*(HANDLE *)a2, a4, v5, &v24, 0)
      && v24 )
    {
      *(_QWORD *)(*((_QWORD *)a1 + 1006) + 1608LL) += v5;
      goto LABEL_42;
    }
    goto LABEL_41;
  }
  if ( *(_QWORD *)(v10 + 1624) == -1 )
  {
    if ( !ReadFile(*(HANDLE *)a2, v11, 0x4000u, &v25, 0) )
      goto LABEL_41;
    v13 = v25;
    if ( !v25 )
      goto LABEL_41;
    *(_WORD *)(*((_QWORD *)a1 + 1006) + 50LL) ^= (*(_WORD *)(*((_QWORD *)a1 + 1006) + 50LL) ^ (8 * (v25 != 0x4000))) & 8;
    *(_QWORD *)(*((_QWORD *)a1 + 1006) + 1624LL) = (int)(v13 - 1);
  }
  v14 = *((_QWORD *)a1 + 1006);
  if ( (*(_BYTE *)(v14 + 50) & 8) != 0 && *(_QWORD *)(v14 + 1608) > *(_QWORD *)(v14 + 1624) )
  {
LABEL_41:
    v8 = 100;
    goto LABEL_42;
  }
  if ( *(_QWORD *)(v14 + 1608) < *(_QWORD *)(v14 + 1616)
    || (unsigned __int64)(*(_QWORD *)(v14 + 1608) + (int)v5) > *(_QWORD *)(v14 + 1624) )
  {
    v15 = *(_QWORD *)(v14 + 1608);
    if ( v15 >= 0x800 )
      v16 = v15 - 2048;
    else
      v16 = 0;
    v17 = *((_QWORD *)a1 + 1006);
    v18 = *(_QWORD *)(v17 + 1864);
    *(_QWORD *)(v17 + 1864) = 0;
    if ( *((_DWORD *)a2 + 16) )
      *((_QWORD *)a2 + 7) = v16;
    else
      bcpSeek64(a1, a2, v16);
    *(_QWORD *)(*((_QWORD *)a1 + 1006) + 1864LL) = v18;
    if ( !ReadFile(*(HANDLE *)a2, *(LPVOID *)(*((_QWORD *)a1 + 1006) + 1864LL), 0x4000u, &v26, 0) )
      goto LABEL_41;
    v19 = v26;
    if ( !v26 )
      goto LABEL_41;
    *(_WORD *)(*((_QWORD *)a1 + 1006) + 50LL) ^= (*(_WORD *)(*((_QWORD *)a1 + 1006) + 50LL) ^ (8 * (v26 != 0x4000))) & 8;
    *(_QWORD *)(*((_QWORD *)a1 + 1006) + 1616LL) = v16;
    *(_QWORD *)(*((_QWORD *)a1 + 1006) + 1624LL) = *(_QWORD *)(*((_QWORD *)a1 + 1006) + 1616LL) + v19 - 1;
  }
  if ( !a4 )
    goto LABEL_42;
  v20 = (_QWORD *)*((_QWORD *)a1 + 1006);
  if ( v20[201] >= v20[202] )
  {
    memcpy(a4, (const void *)(v20[201] + v20[233] - v20[202]), v5);
    *(_QWORD *)(*((_QWORD *)a1 + 1006) + 1608LL) += v5;
    goto LABEL_42;
  }
  if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    bidTraceW(off_383B43238[0], 7916585, off_383B49128[0], 2147942934LL);
  v8 = -1;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( off_383B49120[0] )
      bidTraceW(off_383B43238[0], 7917577, off_383B49120[0], 7732);
    goto LABEL_42;
  }
  return v8;
}

```

## disassembly

```asm
0x383976a90  mov     [rsp+arg_0], rbx
0x383976a95  mov     [rsp+arg_10], rsi
0x383976a9a  push    rdi
0x383976a9b  push    r12
0x383976a9d  push    r13
0x383976a9f  push    r14
0x383976aa1  push    r15
0x383976aa3  sub     rsp, 40h
0x383976aa7  mov     r12, r9
0x383976aaa  mov     r14d, r8d
0x383976aad  mov     rbx, rdx
0x383976ab0  mov     rsi, rcx
0x383976ab3  xor     edi, edi
0x383976ab5  cmp     [rdx+40h], edi
0x383976ab8  jz      short loc_383976AFF
0x383976aba  mov     rcx, [rdx+38h]
0x383976abe  lea     rax, [r14+rcx]
0x383976ac2  cmp     rax, rcx
0x383976ac5  jb      loc_383976E2A
0x383976acb  cmp     rax, [rdx+20h]
0x383976acf  ja      loc_383976E2A
0x383976ad5  mov     rax, [rdx+10h]
0x383976ad9  lea     rdx, [rax+rcx]; Src
0x383976add  mov     r8d, r14d; Size
0x383976ae0  mov     rcx, r9; void *
0x383976ae3  call    memcpy
0x383976ae8  nop
0x383976ae9  add     [rbx+38h], r14
0x383976aed  jmp     loc_383976E32
0x383976af2  mov     eax, 64h ; 'd'
0x383976af7  movzx   edi, ax
0x383976afa  jmp     loc_383976E32
0x383976aff  mov     rax, [rcx+1F70h]
0x383976b06  mov     rdx, [rax+748h]; lpBuffer
0x383976b0d  test    rdx, rdx
0x383976b10  jnz     short loc_383976B42
0x383976b12  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x383976b17  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x383976b1c  mov     r8d, r14d; nNumberOfBytesToRead
0x383976b1f  mov     rdx, r12; lpBuffer
0x383976b22  mov     rcx, [rbx]; hFile
0x383976b25  call    cs:__imp_ReadFile
0x383976b2b  test    eax, eax
0x383976b2d  jz      loc_383976E2A
0x383976b33  cmp     [rsp+68h+NumberOfBytesRead], edi
0x383976b37  jnz     loc_383976E32
0x383976b3d  jmp     loc_383976E2A
0x383976b42  cmp     r14d, 3800h
0x383976b49  jb      short loc_383976BC5
0x383976b4b  mov     edx, [rax+648h]; lDistanceToMove
0x383976b51  mov     rax, [rax+648h]
0x383976b58  shr     rax, 20h
0x383976b5c  mov     [rsp+68h+DistanceToMoveHigh], eax
0x383976b60  xor     r9d, r9d; dwMoveMethod
0x383976b63  lea     r8, [rsp+68h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x383976b68  mov     rcx, [rbx]; hFile
0x383976b6b  call    cs:__imp_SetFilePointer
0x383976b71  cmp     eax, 0FFFFFFFFh
0x383976b74  jnz     short loc_383976B84
0x383976b76  call    cs:__imp_GetLastError
0x383976b7c  test    eax, eax
0x383976b7e  jnz     loc_383976E2A
0x383976b84  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x383976b89  lea     r9, [rsp+68h+var_34]; lpNumberOfBytesRead
0x383976b8e  mov     r8d, r14d; nNumberOfBytesToRead
0x383976b91  mov     rdx, r12; lpBuffer
0x383976b94  mov     rcx, [rbx]; hFile
0x383976b97  call    cs:__imp_ReadFile
0x383976b9d  test    eax, eax
0x383976b9f  jz      loc_383976E2A
0x383976ba5  cmp     [rsp+68h+var_34], edi
0x383976ba9  jz      loc_383976E2A
0x383976baf  mov     rcx, [rsi+1F70h]
0x383976bb6  mov     rax, r14
0x383976bb9  add     [rcx+648h], rax
0x383976bc0  jmp     loc_383976E32
0x383976bc5  cmp     qword ptr [rax+658h], 0FFFFFFFFFFFFFFFFh
0x383976bcd  jnz     short loc_383976C32
0x383976bcf  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x383976bd4  lea     r9, [rsp+68h+var_30]; lpNumberOfBytesRead
0x383976bd9  mov     r8d, 4000h; nNumberOfBytesToRead
0x383976bdf  mov     rcx, [rbx]; hFile
0x383976be2  call    cs:__imp_ReadFile
0x383976be8  test    eax, eax
0x383976bea  jz      loc_383976E2A
0x383976bf0  mov     edx, [rsp+68h+var_30]
0x383976bf4  test    edx, edx
0x383976bf6  jz      loc_383976E2A
0x383976bfc  mov     rcx, [rsi+1F70h]
0x383976c03  mov     eax, edi
0x383976c05  cmp     edx, 4000h
0x383976c0b  setnz   al
0x383976c0e  shl     ax, 3
0x383976c12  xor     ax, [rcx+32h]
0x383976c16  and     ax, 8
0x383976c1a  xor     [rcx+32h], ax
0x383976c1e  lea     eax, [rdx-1]
0x383976c21  movsxd  rcx, eax
0x383976c24  mov     rax, [rsi+1F70h]
0x383976c2b  mov     [rax+658h], rcx
0x383976c32  mov     r15, [rsi+1F70h]
0x383976c39  test    byte ptr [r15+32h], 8
0x383976c3e  jz      short loc_383976C54
0x383976c40  mov     rax, [r15+658h]
0x383976c47  cmp     [r15+648h], rax
0x383976c4e  ja      loc_383976E2A
0x383976c54  mov     rax, [r15+650h]
0x383976c5b  cmp     [r15+648h], rax
0x383976c62  jb      short loc_383976C7B
0x383976c64  movsxd  rax, r14d
0x383976c67  add     rax, [r15+648h]
0x383976c6e  cmp     rax, [r15+658h]
0x383976c75  jbe     loc_383976D5D
0x383976c7b  mov     r15, [r15+648h]
0x383976c82  cmp     r15, 800h
0x383976c89  jnb     short loc_383976C90
0x383976c8b  mov     r15, rdi
0x383976c8e  jmp     short loc_383976C97
0x383976c90  add     r15, 0FFFFFFFFFFFFF800h
0x383976c97  mov     rax, [rsi+1F70h]
0x383976c9e  mov     r13, [rax+748h]
0x383976ca5  mov     [rax+748h], rdi
0x383976cac  cmp     [rbx+40h], edi
0x383976caf  jz      short loc_383976CB7
0x383976cb1  mov     [rbx+38h], r15
0x383976cb5  jmp     short loc_383976CC5
0x383976cb7  mov     r8, r15; unsigned __int64
0x383976cba  mov     rdx, rbx; struct BCPFILE *
0x383976cbd  mov     rcx, rsi; struct tagDBC *
0x383976cc0  call    ?bcpSeek64@@YAFPEAUtagDBC@@PEAUBCPFILE@@_K@Z; bcpSeek64(tagDBC *,BCPFILE *,unsigned __int64)
0x383976cc5  mov     rax, [rsi+1F70h]
0x383976ccc  mov     [rax+748h], r13
0x383976cd3  mov     rax, [rsi+1F70h]
0x383976cda  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x383976cdf  lea     r9, [rsp+68h+var_2C]; lpNumberOfBytesRead
0x383976ce4  mov     r8d, 4000h; nNumberOfBytesToRead
0x383976cea  mov     rdx, [rax+748h]; lpBuffer
0x383976cf1  mov     rcx, [rbx]; hFile
0x383976cf4  call    cs:__imp_ReadFile
0x383976cfa  test    eax, eax
0x383976cfc  jz      loc_383976E2A
0x383976d02  mov     r8d, [rsp+68h+var_2C]
0x383976d07  test    r8d, r8d
0x383976d0a  jz      loc_383976E2A
0x383976d10  mov     rcx, [rsi+1F70h]
0x383976d17  mov     eax, edi
0x383976d19  cmp     r8d, 4000h
0x383976d20  setnz   al
0x383976d23  shl     ax, 3
0x383976d27  xor     ax, [rcx+32h]
0x383976d2b  and     ax, 8
0x383976d2f  xor     [rcx+32h], ax
0x383976d33  mov     rax, [rsi+1F70h]
0x383976d3a  mov     [rax+650h], r15
0x383976d41  mov     rdx, [rsi+1F70h]
0x383976d48  mov     rax, [rdx+650h]
0x383976d4f  lea     rcx, [r8-1]
0x383976d53  add     rcx, rax
0x383976d56  mov     [rdx+658h], rcx
0x383976d5d  test    r12, r12
0x383976d60  jz      loc_383976E32
0x383976d66  mov     rcx, [rsi+1F70h]
0x383976d6d  mov     rax, [rcx+650h]
0x383976d74  cmp     [rcx+648h], rax
0x383976d7b  jnb     short loc_383976DF7
0x383976d7d  test    byte ptr cs:_bidGblFlags, 2
0x383976d84  jz      short loc_383976DB8
0x383976d86  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383976d8d  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383976d94  test    rax, rax
0x383976d97  jz      short loc_383976DB8
0x383976d99  mov     dword ptr [rsp+68h+lpOverlapped], 1E33h
0x383976da1  mov     r9d, 80070216h
0x383976da7  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383976dae  mov     edx, 78CC29h
0x383976db3  call    _bidTraceW
0x383976db8  or      eax, 0FFFFFFFFh
0x383976dbb  movzx   edi, ax
0x383976dbe  test    byte ptr cs:_bidGblFlags, 2
0x383976dc5  jz      loc_383976E70
0x383976dcb  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383976dd2  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383976dd9  test    rax, rax
0x383976ddc  jz      short loc_383976E32
0x383976dde  mov     r9d, 1E34h
0x383976de4  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383976deb  mov     edx, 78D009h
0x383976df0  call    _bidTraceW
0x383976df5  jmp     short loc_383976E32
0x383976df7  mov     rax, rcx
0x383976dfa  mov     rdx, [rcx+748h]
0x383976e01  sub     rdx, [rcx+650h]
0x383976e08  add     rdx, [rcx+648h]; Src
0x383976e0f  mov     r8, r14; Size
0x383976e12  mov     rcx, r12; void *
0x383976e15  call    memcpy
0x383976e1a  mov     r11, [rsi+1F70h]
0x383976e21  add     [r11+648h], r14
0x383976e28  jmp     short loc_383976E32
0x383976e2a  mov     eax, 64h ; 'd'
0x383976e2f  movzx   edi, ax
0x383976e32  test    byte ptr cs:_bidGblFlags, 2
0x383976e39  jz      short loc_383976E70
0x383976e3b  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383976e42  mov     r8, cs:off_383B494E8; "<ODBC|DRIVER|RET> %d{SQLRETURN}\n"
0x383976e49  test    di, di
0x383976e4c  jnz     short loc_383976E57
0x383976e4e  test    byte ptr cs:_bidGblFlags, 40h
0x383976e55  jz      short loc_383976E70
0x383976e57  mov     edx, 790C01h
0x383976e5c  mov     eax, 790C21h
0x383976e61  test    di, di
0x383976e64  cmovnz  edx, eax
0x383976e67  movsx   r9d, di
0x383976e6b  call    _bidTraceW
0x383976e70  movzx   eax, di
0x383976e73  mov     rbx, [rsp+68h+arg_0]
0x383976e78  mov     rsi, [rsp+68h+arg_10]
0x383976e80  add     rsp, 40h
0x383976e84  pop     r15
0x383976e86  pop     r14
0x383976e88  pop     r13
0x383976e8a  pop     r12
0x383976e8c  pop     rdi
0x383976e8d  retn
```
