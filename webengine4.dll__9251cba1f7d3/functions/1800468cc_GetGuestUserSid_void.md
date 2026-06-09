# GetGuestUserSid(void)

- ea: `0x1800468cc`
- end: `0x180046a40`
- name: `?GetGuestUserSid@@YAPEAXXZ`
- size: `372`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180047214`

## callees

- `0x1800468cc`
- `0x18004c3dd`
- `0x18004c425`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x180046930`
- `ADVAPI32!IsValidSid` at `0x180046930`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x180046982`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x180046982`
- `ADVAPI32!GetSidLengthRequired` at `0x180046960`
- `ADVAPI32!GetSidLengthRequired` at `0x180046960`
- `ADVAPI32!GetSidSubAuthority` at `0x1800469ba`
- `ADVAPI32!GetSidSubAuthority` at `0x1800469cd`
- `ADVAPI32!GetSidSubAuthority` at `0x1800469ed`
- `ADVAPI32!GetSidSubAuthority` at `0x1800469ba`
- `ADVAPI32!GetSidSubAuthority` at `0x1800469cd`
- `ADVAPI32!GetSidSubAuthority` at `0x1800469ed`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180046941`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180046941`
- `ADVAPI32!InitializeSid` at `0x180046999`
- `ADVAPI32!InitializeSid` at `0x180046999`

## pseudocode

```c
void *GetGuestUserSid(void)
{
  void *v0; // rsi
  unsigned int LastWin32Error; // ebx
  signed int v2; // eax
  void *v3; // rdi
  PUCHAR SidSubAuthorityCount; // rax
  PUCHAR v5; // r14
  UCHAR v6; // al
  DWORD SidLengthRequired; // eax
  struct _SID_IDENTIFIER_AUTHORITY *SidIdentifierAuthority; // rax
  DWORD v9; // eax
  DWORD v10; // ebp
  PDWORD SidSubAuthority; // r15
  PDWORD v12; // rax
  PDWORD v13; // rax
  LPVOID Buffer; // [rsp+40h] [rbp+8h] BYREF

  Buffer = 0;
  v0 = 0;
  LastWin32Error = 0;
  v2 = NetUserModalsGet_0(0, 2u, (LPBYTE *)&Buffer);
  if ( v2 )
  {
    LastWin32Error = (unsigned __int16)v2 | 0x80070000;
    if ( v2 <= 0 )
      LastWin32Error = v2;
  }
  else
  {
    if ( !Buffer )
      goto LABEL_26;
    v3 = (void *)*((_QWORD *)Buffer + 1);
    if ( v3 )
    {
      if ( IsValidSid(*((PSID *)Buffer + 1)) )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(v3);
        v5 = SidSubAuthorityCount;
        if ( SidSubAuthorityCount )
        {
          v6 = *SidSubAuthorityCount;
          if ( v6 )
          {
            SidLengthRequired = GetSidLengthRequired(v6 + 1);
            v0 = MemAllocClear(SidLengthRequired);
            if ( !v0 )
            {
              LastWin32Error = -2147024882;
              goto LABEL_22;
            }
            SidIdentifierAuthority = GetSidIdentifierAuthority(v3);
            if ( SidIdentifierAuthority )
            {
              if ( InitializeSid(v0, SidIdentifierAuthority, *v5 + 1) )
              {
                LOBYTE(v9) = *v5;
                v10 = 0;
                if ( *v5 )
                {
                  while ( 1 )
                  {
                    SidSubAuthority = GetSidSubAuthority(v3, v10);
                    if ( !SidSubAuthority )
                      break;
                    v12 = GetSidSubAuthority(v0, v10);
                    if ( !v12 )
                      break;
                    ++v10;
                    *v12 = *SidSubAuthority;
                    v9 = *v5;
                    if ( v10 >= v9 )
                      goto LABEL_19;
                  }
                }
                else
                {
LABEL_19:
                  v13 = GetSidSubAuthority(v0, (unsigned __int8)v9);
                  if ( v13 )
                  {
                    *v13 = 501;
                    goto LABEL_22;
                  }
                }
              }
              LastWin32Error = GetLastWin32Error();
              goto LABEL_22;
            }
          }
        }
      }
    }
    LastWin32Error = -2147418113;
  }
LABEL_22:
  if ( Buffer )
    NetApiBufferFree_0(Buffer);
  if ( !LastWin32Error )
    return v0;
LABEL_26:
  MemFree(v0);
  return 0;
}

```

## disassembly

```asm
0x1800468cc  mov     rax, rsp
0x1800468cf  mov     [rax+10h], rbx
0x1800468d3  mov     [rax+18h], rbp
0x1800468d7  mov     [rax+20h], rsi
0x1800468db  push    rdi
0x1800468dc  push    r14
0x1800468de  push    r15
0x1800468e0  sub     rsp, 20h
0x1800468e4  and     qword ptr [rax+8], 0
0x1800468e9  lea     r8, [rax+8]; bufptr
0x1800468ed  xor     esi, esi
0x1800468ef  xor     ecx, ecx; servername
0x1800468f1  xor     ebx, ebx
0x1800468f3  lea     edx, [rsi+2]; level
0x1800468f6  call    NetUserModalsGet_0
0x1800468fb  test    eax, eax
0x1800468fd  jz      short loc_180046912
0x1800468ff  movzx   ebx, ax
0x180046902  or      ebx, 80070000h
0x180046908  test    eax, eax
0x18004690a  cmovle  ebx, eax
0x18004690d  jmp     loc_180046A05
0x180046912  mov     rcx, [rsp+38h+Buffer]
0x180046917  test    rcx, rcx
0x18004691a  jz      loc_180046A1D
0x180046920  mov     rdi, [rcx+8]
0x180046924  test    rdi, rdi
0x180046927  jz      loc_180046A00
0x18004692d  mov     rcx, rdi; pSid
0x180046930  call    cs:__imp_IsValidSid
0x180046936  test    eax, eax
0x180046938  jz      loc_180046A00
0x18004693e  mov     rcx, rdi; pSid
0x180046941  call    cs:__imp_GetSidSubAuthorityCount
0x180046947  mov     r14, rax
0x18004694a  test    rax, rax
0x18004694d  jz      loc_180046A00
0x180046953  mov     al, [rax]
0x180046955  test    al, al
0x180046957  jz      loc_180046A00
0x18004695d  lea     ecx, [rax+1]; nSubAuthorityCount
0x180046960  call    cs:__imp_GetSidLengthRequired
0x180046966  mov     ecx, eax; unsigned __int64
0x180046968  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18004696d  mov     rsi, rax
0x180046970  test    rax, rax
0x180046973  jnz     short loc_18004697F
0x180046975  mov     ebx, 8007000Eh
0x18004697a  jmp     loc_180046A05
0x18004697f  mov     rcx, rdi; pSid
0x180046982  call    cs:__imp_GetSidIdentifierAuthority
0x180046988  test    rax, rax
0x18004698b  jz      short loc_180046A00
0x18004698d  mov     r8b, [r14]
0x180046990  mov     rdx, rax; pIdentifierAuthority
0x180046993  inc     r8b; nSubAuthorityCount
0x180046996  mov     rcx, rsi; Sid
0x180046999  call    cs:__imp_InitializeSid
0x18004699f  test    eax, eax
0x1800469a1  jnz     short loc_1800469AC
0x1800469a3  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800469a8  mov     ebx, eax
0x1800469aa  jmp     short loc_180046A05
0x1800469ac  mov     al, [r14]
0x1800469af  xor     ebp, ebp
0x1800469b1  test    al, al
0x1800469b3  jz      short loc_1800469E7
0x1800469b5  mov     edx, ebp; nSubAuthority
0x1800469b7  mov     rcx, rdi; pSid
0x1800469ba  call    cs:__imp_GetSidSubAuthority
0x1800469c0  mov     r15, rax
0x1800469c3  test    rax, rax
0x1800469c6  jz      short loc_1800469A3
0x1800469c8  mov     edx, ebp; nSubAuthority
0x1800469ca  mov     rcx, rsi; pSid
0x1800469cd  call    cs:__imp_GetSidSubAuthority
0x1800469d3  test    rax, rax
0x1800469d6  jz      short loc_1800469A3
0x1800469d8  mov     ecx, [r15]
0x1800469db  inc     ebp
0x1800469dd  mov     [rax], ecx
0x1800469df  movzx   eax, byte ptr [r14]
0x1800469e3  cmp     ebp, eax
0x1800469e5  jb      short loc_1800469B5
0x1800469e7  movzx   edx, al; nSubAuthority
0x1800469ea  mov     rcx, rsi; pSid
0x1800469ed  call    cs:__imp_GetSidSubAuthority
0x1800469f3  test    rax, rax
0x1800469f6  jz      short loc_1800469A3
0x1800469f8  mov     dword ptr [rax], 1F5h
0x1800469fe  jmp     short loc_180046A05
0x180046a00  mov     ebx, 8000FFFFh
0x180046a05  mov     rcx, [rsp+38h+Buffer]; Buffer
0x180046a0a  test    rcx, rcx
0x180046a0d  jz      short loc_180046A14
0x180046a0f  call    NetApiBufferFree_0
0x180046a14  test    ebx, ebx
0x180046a16  jnz     short loc_180046A1D
0x180046a18  mov     rax, rsi
0x180046a1b  jmp     short loc_180046A27
0x180046a1d  mov     rcx, rsi; lpMem
0x180046a20  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180046a25  xor     eax, eax
0x180046a27  mov     rbx, [rsp+38h+arg_8]
0x180046a2c  mov     rbp, [rsp+38h+arg_10]
0x180046a31  mov     rsi, [rsp+38h+arg_18]
0x180046a36  add     rsp, 20h
0x180046a3a  pop     r15
0x180046a3c  pop     r14
0x180046a3e  pop     rdi
0x180046a3f  retn
```
