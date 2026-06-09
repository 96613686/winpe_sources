# UwfServicingEnableServicingUser(bool)

- ea: `0x1800027c8`
- end: `0x180002870`
- name: `?UwfServicingEnableServicingUser@@YAJ_N@Z`
- size: `168`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180003540`

## callees

- `0x1800027c8`
- `0x180002960`

## import_xrefs

- `msvcrt!free` at `0x180002845`
- `msvcrt!free` at `0x180002845`
- `samcli!NetUserSetInfo` at `0x180002832`
- `samcli!NetUserSetInfo` at `0x180002832`
- `samcli!NetUserGetInfo` at `0x1800027fd`
- `samcli!NetUserGetInfo` at `0x1800027fd`
- `netutils!NetApiBufferFree` at `0x180002854`
- `netutils!NetApiBufferFree` at `0x180002854`

## pseudocode

```c
__int64 __fastcall UwfServicingEnableServicingUser()
{
  signed int Info; // ebx
  int v1; // ecx
  int buf; // [rsp+50h] [rbp+18h] BYREF
  DWORD parm_err; // [rsp+58h] [rbp+20h] BYREF
  LPCWSTR username; // [rsp+60h] [rbp+28h] BYREF
  LPBYTE bufptr; // [rsp+68h] [rbp+30h] BYREF

  Info = 0;
  bufptr = 0;
  buf = 0;
  username = 0;
  if ( (int)UwfServicingGetUserName((unsigned __int16 **)&username) >= 0 )
  {
    Info = NetUserGetInfo(0, username, 1u, &bufptr);
    if ( !Info )
    {
      v1 = *((_DWORD *)bufptr + 10) | 2;
      parm_err = 0;
      buf = v1;
      Info = NetUserSetInfo(0, username, 0x3F0u, (LPBYTE)&buf, &parm_err);
    }
  }
  if ( username )
    free((void *)username);
  if ( bufptr )
    NetApiBufferFree(bufptr);
  if ( Info > 0 )
    return (unsigned __int16)Info | 0x80070000;
  return (unsigned int)Info;
}

```

## disassembly

```asm
0x1800027c8  mov     byte ptr [rsp-10h+buf], cl
0x1800027cc  push    rbp
0x1800027cd  push    rbx
0x1800027ce  mov     rbp, rsp
0x1800027d1  sub     rsp, 38h
0x1800027d5  xor     ebx, ebx
0x1800027d7  lea     rcx, [rbp+username]; unsigned __int16 **
0x1800027db  mov     [rbp+bufptr], rbx
0x1800027df  mov     [rbp+buf], ebx
0x1800027e2  mov     [rbp+username], rbx
0x1800027e6  call    ?UwfServicingGetUserName@@YAJPEAPEAG@Z; UwfServicingGetUserName(ushort * *)
0x1800027eb  test    eax, eax
0x1800027ed  js      short loc_18000283A
0x1800027ef  mov     rdx, [rbp+username]; username
0x1800027f3  lea     r9, [rbp+bufptr]; bufptr
0x1800027f7  lea     r8d, [rbx+1]; level
0x1800027fb  xor     ecx, ecx; servername
0x1800027fd  call    cs:__imp_NetUserGetInfo
0x180002803  mov     ebx, eax
0x180002805  test    eax, eax
0x180002807  jnz     short loc_18000283A
0x180002809  mov     rax, [rbp+bufptr]
0x18000280d  lea     r9, [rbp+buf]; buf
0x180002811  mov     rdx, [rbp+username]; username
0x180002815  mov     r8d, 3F0h; level
0x18000281b  mov     ecx, [rax+28h]
0x18000281e  lea     rax, [rbp+arg_8]
0x180002822  or      ecx, 2
0x180002825  mov     [rbp+arg_8], ebx
0x180002828  mov     [rbp+buf], ecx
0x18000282b  xor     ecx, ecx; servername
0x18000282d  mov     [rsp+38h+parm_err], rax; parm_err
0x180002832  call    cs:__imp_NetUserSetInfo
0x180002838  mov     ebx, eax
0x18000283a  cmp     [rbp+username], 0
0x18000283f  jz      short loc_18000284B
0x180002841  mov     rcx, [rbp+username]; Block
0x180002845  call    cs:__imp_free
0x18000284b  mov     rcx, [rbp+bufptr]; Buffer
0x18000284f  test    rcx, rcx
0x180002852  jz      short loc_18000285A
0x180002854  call    cs:__imp_NetApiBufferFree
0x18000285a  test    ebx, ebx
0x18000285c  jle     short loc_180002867
0x18000285e  movzx   ebx, bx
0x180002861  or      ebx, 80070000h
0x180002867  mov     eax, ebx
0x180002869  add     rsp, 38h
0x18000286d  pop     rbx
0x18000286e  pop     rbp
0x18000286f  retn
```
