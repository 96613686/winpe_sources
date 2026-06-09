# PfPrUpdateConsoleSession

- ea: `0x18008cff8`
- end: `0x18008d17c`
- name: `PfPrUpdateConsoleSession`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180026cd0`

## callees

- `0x180051ec4`
- `0x18008cff8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008d11c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008d11c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008d154`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008d154`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008d106`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008d106`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008d0f5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008d12d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008d0f5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008d12d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008d140`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008d140`

## pseudocode

```c
__int64 __fastcall PfPrUpdateConsoleSession(__int64 a1, _DWORD *a2)
{
  unsigned int v3; // r10d
  unsigned int *v4; // r8
  unsigned int v5; // r9d
  void *v6; // rdi
  unsigned int v7; // ecx
  unsigned int v8; // ebx
  unsigned int v9; // esi
  int v10; // r8d
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // r15d
  int v14; // ebx
  DWORD LengthSid; // ebp
  __int64 v16; // r14

  if ( (*a2 & 0x1F000) != 0x16000 )
  {
    v10 = a2[4];
    if ( ((v10 - 1) & 0xFFFFFFFB) != 0 )
    {
      if ( ((v10 - 2) & 0xFFFFFFFB) != 0 )
        return 0;
      v7 = a2[5];
      v6 = a2 + 6;
      v11 = 0;
      v9 = 14;
      if ( v10 == 6 )
        v11 = 0x80000000;
      v8 = v11;
      goto LABEL_18;
    }
    v7 = a2[5];
    v6 = a2 + 6;
    v12 = 0;
    if ( v10 == 5 )
      v12 = 0x80000000;
    v8 = v12;
    goto LABEL_17;
  }
  v3 = a2[6];
  v4 = a2 + 7;
  v5 = 0;
  if ( v3 )
  {
    while ( (v4[2] & 1) == 0 )
    {
      ++v5;
      v4 = (unsigned int *)((char *)v4 + *v4);
      if ( v5 >= v3 )
        goto LABEL_5;
    }
    goto LABEL_7;
  }
LABEL_5:
  if ( v5 < v3 )
  {
LABEL_7:
    if ( v4[2] >= 2 )
      return 0;
    v7 = v4[1];
    v6 = v4 + 3;
    v8 = 0x80000000;
LABEL_17:
    v9 = 13;
    goto LABEL_18;
  }
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 14;
LABEL_18:
  v13 = a2[2];
  v14 = v7 & 0x3FFFFFFF | v8;
  LengthSid = 0;
  if ( v9 == 14 )
    v16 = *(_QWORD *)&PfSvcGlobals + 1856LL;
  else
    v16 = *(_QWORD *)&PfSvcGlobals + 1840LL;
  if ( v6 && IsValidSid(v6) )
  {
    v14 |= 0x40000000u;
    LengthSid = GetLengthSid(v6);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&PfSvcGlobals + 1800LL));
  *(_DWORD *)v16 = v14;
  if ( v6 && IsValidSid(v6) )
    CopySid(LengthSid, *(PSID *)(v16 + 8), v6);
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&PfSvcGlobals + 1800LL));
  PfSvProcessConsoleAction(a1 - 1176, v9, v13);
  return 0;
}

```

## disassembly

```asm
0x18008cff8  push    rbx
0x18008cffa  push    rbp
0x18008cffb  push    rsi
0x18008cffc  push    rdi
0x18008cffd  push    r13
0x18008cfff  push    r14
0x18008d001  push    r15
0x18008d003  sub     rsp, 20h
0x18008d007  mov     eax, [rdx]
0x18008d009  mov     r13, rcx
0x18008d00c  and     eax, 1F000h
0x18008d011  mov     r11d, 0Eh
0x18008d017  cmp     rax, 16000h
0x18008d01d  jnz     short loc_18008D06E
0x18008d01f  mov     r10d, [rdx+18h]
0x18008d023  lea     r8, [rdx+1Ch]
0x18008d027  xor     r9d, r9d
0x18008d02a  test    r10d, r10d
0x18008d02d  jz      short loc_18008D044
0x18008d02f  test    byte ptr [r8+8], 1
0x18008d034  jnz     short loc_18008D054
0x18008d036  mov     eax, [r8]
0x18008d039  inc     r9d
0x18008d03c  add     r8, rax
0x18008d03f  cmp     r9d, r10d
0x18008d042  jb      short loc_18008D02F
0x18008d044  cmp     r9d, r10d
0x18008d047  jb      short loc_18008D054
0x18008d049  xor     edi, edi
0x18008d04b  xor     ecx, ecx
0x18008d04d  xor     ebx, ebx
0x18008d04f  mov     esi, r11d
0x18008d052  jmp     short loc_18008D0C3
0x18008d054  cmp     dword ptr [r8+8], 2
0x18008d059  jnb     loc_18008D16B
0x18008d05f  mov     ecx, [r8+4]
0x18008d063  lea     rdi, [r8+0Ch]
0x18008d067  mov     ebx, 80000000h
0x18008d06c  jmp     short loc_18008D0BE
0x18008d06e  mov     r8d, [rdx+10h]
0x18008d072  mov     ecx, 0FFFFFFFBh
0x18008d077  lea     eax, [r8-1]
0x18008d07b  test    ecx, eax
0x18008d07d  jz      short loc_18008D0A7
0x18008d07f  lea     eax, [r8-2]
0x18008d083  test    ecx, eax
0x18008d085  jnz     loc_18008D16B
0x18008d08b  mov     ecx, [rdx+14h]
0x18008d08e  lea     rdi, [rdx+18h]
0x18008d092  xor     eax, eax
0x18008d094  mov     ebx, 80000000h
0x18008d099  cmp     r8d, 6
0x18008d09d  mov     esi, r11d
0x18008d0a0  cmovz   eax, ebx
0x18008d0a3  mov     ebx, eax
0x18008d0a5  jmp     short loc_18008D0C3
0x18008d0a7  mov     ecx, [rdx+14h]
0x18008d0aa  lea     rdi, [rdx+18h]
0x18008d0ae  xor     eax, eax
0x18008d0b0  mov     ebx, 80000000h
0x18008d0b5  cmp     r8d, 5
0x18008d0b9  cmovz   eax, ebx
0x18008d0bc  mov     ebx, eax
0x18008d0be  mov     esi, 0Dh
0x18008d0c3  mov     r15d, [rdx+8]
0x18008d0c7  and     ecx, 3FFFFFFFh
0x18008d0cd  mov     r14, cs:PfSvcGlobals
0x18008d0d4  or      ebx, ecx
0x18008d0d6  xor     ebp, ebp
0x18008d0d8  cmp     esi, r11d
0x18008d0db  jnz     short loc_18008D0E6
0x18008d0dd  add     r14, 740h
0x18008d0e4  jmp     short loc_18008D0ED
0x18008d0e6  add     r14, 730h
0x18008d0ed  test    rdi, rdi
0x18008d0f0  jz      short loc_18008D10E
0x18008d0f2  mov     rcx, rdi; pSid
0x18008d0f5  call    cs:__imp_IsValidSid
0x18008d0fb  test    eax, eax
0x18008d0fd  jz      short loc_18008D10E
0x18008d0ff  bts     ebx, 1Eh
0x18008d103  mov     rcx, rdi; pSid
0x18008d106  call    cs:__imp_GetLengthSid
0x18008d10c  mov     ebp, eax
0x18008d10e  mov     rcx, cs:PfSvcGlobals
0x18008d115  add     rcx, 708h; lpCriticalSection
0x18008d11c  call    cs:__imp_EnterCriticalSection
0x18008d122  mov     [r14], ebx
0x18008d125  test    rdi, rdi
0x18008d128  jz      short loc_18008D146
0x18008d12a  mov     rcx, rdi; pSid
0x18008d12d  call    cs:__imp_IsValidSid
0x18008d133  test    eax, eax
0x18008d135  jz      short loc_18008D146
0x18008d137  mov     rdx, [r14+8]; pDestinationSid
0x18008d13b  mov     r8, rdi; pSourceSid
0x18008d13e  mov     ecx, ebp; nDestinationSidLength
0x18008d140  call    cs:__imp_CopySid
0x18008d146  mov     rcx, cs:PfSvcGlobals
0x18008d14d  add     rcx, 708h; lpCriticalSection
0x18008d154  call    cs:__imp_LeaveCriticalSection
0x18008d15a  lea     rcx, [r13-498h]
0x18008d161  mov     r8d, r15d
0x18008d164  mov     edx, esi
0x18008d166  call    PfSvProcessConsoleAction
0x18008d16b  xor     eax, eax
0x18008d16d  add     rsp, 20h
0x18008d171  pop     r15
0x18008d173  pop     r14
0x18008d175  pop     r13
0x18008d177  pop     rdi
0x18008d178  pop     rsi
0x18008d179  pop     rbp
0x18008d17a  pop     rbx
0x18008d17b  retn
```
