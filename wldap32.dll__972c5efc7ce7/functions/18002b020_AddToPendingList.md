# AddToPendingList

- ea: `0x18002b020`
- end: `0x18002b19e`
- name: `AddToPendingList`
- size: `382`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180012ab0`
- `0x1800164a0`
- `0x18002d1a8`
- `0x18003a274`
- `0x18003c5bc`
- `0x18003e508`
- `0x18003f138`
- `0x180047254`
- `0x1800491d4`

## callees

- `0x1800037a8`
- `0x18002b020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b035`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b035`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b07d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b07d`

## string_xrefs

- `0x18002b18d`: `LdapAddToPendingList couldn't bump for request 0x%x.\n`
- `0x18002b10f`: `LdapAddToPendingList bumping outstanding to 0x%x for 0x%x.\n`
- `0x18002b14a`: `LdapAddToPendingList bumping outstanding to 0x%x for 0x%x.\n`

## pseudocode

```c
__int64 __fastcall AddToPendingList(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebp
  __int64 v6; // rcx
  unsigned __int16 v7; // dx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  if ( a2 == *(_QWORD *)(a1 + 32) )
  {
    v4 = 0;
    _InterlockedAdd((volatile signed __int32 *)(a2 + 472), 1u);
    ++*(_WORD *)(a1 + 182);
    ++*(_DWORD *)(a1 + 152);
    _InterlockedAdd(&GlobalCountOfOpenRequests, 1u);
    _InterlockedAdd64(&qword_180066138, 1u);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
      LDAPClientPrint(
        0x1000000,
        "LdapAddToPendingList bumping outstanding to 0x%x for 0x%x.\n",
        *(unsigned __int16 *)(a1 + 182),
        a1);
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 168);
    v7 = 0;
    if ( v6 )
    {
      while ( v7 < *(_WORD *)(a1 + 176) )
      {
        if ( *(_QWORD *)v6 == a2 )
        {
          _InterlockedAdd(&GlobalCountOfOpenRequests, 1u);
          _InterlockedAdd64(&qword_180066138, 1u);
          _InterlockedAdd((volatile signed __int32 *)(a2 + 472), 1u);
          ++*(_WORD *)(a1 + 182);
          ++*(_DWORD *)(v6 + 48);
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
            LDAPClientPrint(
              0x1000000,
              "LdapAddToPendingList bumping outstanding to 0x%x for 0x%x.\n",
              *(unsigned __int16 *)(a1 + 182),
              a1);
          v4 = 0;
          goto LABEL_3;
        }
        ++v7;
        v6 += 64;
      }
    }
    v4 = 82;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
      LDAPClientPrint(0x1000000, "LdapAddToPendingList couldn't bump for request 0x%x.\n", a1);
  }
LABEL_3:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  return v4;
}

```

## disassembly

```asm
0x18002b020  push    rbx
0x18002b022  push    rbp
0x18002b023  push    rsi
0x18002b024  push    rdi
0x18002b025  push    r14
0x18002b027  sub     rsp, 20h
0x18002b02b  mov     rdi, rcx
0x18002b02e  mov     rsi, rdx
0x18002b031  add     rcx, 30h ; '0'; lpCriticalSection
0x18002b035  call    cs:__imp_EnterCriticalSection
0x18002b03c  nop     dword ptr [rax+rax+00h]
0x18002b041  xor     ebx, ebx
0x18002b043  cmp     rsi, [rdi+20h]
0x18002b047  jnz     short loc_18002B097
0x18002b049  mov     ebp, ebx
0x18002b04b  lea     eax, [rbx+1]
0x18002b04e  lock add [rsi+1D8h], eax
0x18002b055  add     [rdi+0B6h], ax
0x18002b05c  add     [rdi+98h], eax
0x18002b062  lock add cs:GlobalCountOfOpenRequests, eax
0x18002b069  lock add cs:qword_180066138, rax
0x18002b071  cmp     cs:g_fTracingOn, ebx
0x18002b077  jnz     short loc_18002B0ED
0x18002b079  lea     rcx, [rdi+30h]; lpCriticalSection
0x18002b07d  call    cs:__imp_LeaveCriticalSection
0x18002b084  nop     dword ptr [rax+rax+00h]
0x18002b089  mov     eax, ebp
0x18002b08b  add     rsp, 20h
0x18002b08f  pop     r14
0x18002b091  pop     rdi
0x18002b092  pop     rsi
0x18002b093  pop     rbp
0x18002b094  pop     rbx
0x18002b095  retn
0x18002b097  mov     rcx, [rdi+0A8h]
0x18002b09e  movzx   edx, bx
0x18002b0a1  test    rcx, rcx
0x18002b0a4  jz      loc_18002B15B
0x18002b0aa  mov     eax, 1
0x18002b0af  cmp     dx, [rdi+0B0h]
0x18002b0b6  jnb     loc_18002B15B
0x18002b0bc  cmp     [rcx], rsi
0x18002b0bf  jnz     short loc_18002B123
0x18002b0c1  lock add cs:GlobalCountOfOpenRequests, eax
0x18002b0c8  lock add cs:qword_180066138, rax
0x18002b0d0  lock add [rsi+1D8h], eax
0x18002b0d7  add     [rdi+0B6h], ax
0x18002b0de  add     [rcx+30h], eax
0x18002b0e1  cmp     cs:g_fTracingOn, ebx
0x18002b0e7  jnz     short loc_18002B12C
0x18002b0e9  mov     ebp, ebx
0x18002b0eb  jmp     short loc_18002B079
0x18002b0ed  cmp     cs:g_fProviderEnabled, ebx
0x18002b0f3  jz      short loc_18002B079
0x18002b0f5  mov     ecx, 1000000h
0x18002b0fa  test    cs:g_ulTraceFlags, rcx
0x18002b101  jz      loc_18002B079
0x18002b107  movzx   r8d, word ptr [rdi+0B6h]
0x18002b10f  lea     rdx, aLdapaddtopendi_0; "LdapAddToPendingList bumping outstandin"...
0x18002b116  mov     r9, rdi
0x18002b119  call    LDAPClientPrint
0x18002b11e  jmp     loc_18002B079
0x18002b123  add     dx, ax
0x18002b126  add     rcx, 40h ; '@'
0x18002b12a  jmp     short loc_18002B0AF
0x18002b12c  cmp     cs:g_fProviderEnabled, ebx
0x18002b132  jz      short loc_18002B0E9
0x18002b134  mov     ecx, 1000000h
0x18002b139  test    cs:g_ulTraceFlags, rcx
0x18002b140  jz      short loc_18002B0E9
0x18002b142  movzx   r8d, word ptr [rdi+0B6h]
0x18002b14a  lea     rdx, aLdapaddtopendi_0; "LdapAddToPendingList bumping outstandin"...
0x18002b151  mov     r9, rdi
0x18002b154  call    LDAPClientPrint
0x18002b159  jmp     short loc_18002B0E9
0x18002b15b  cmp     cs:g_fTracingOn, ebx
0x18002b161  mov     ebp, 52h ; 'R'
0x18002b166  jz      loc_18002B079
0x18002b16c  cmp     cs:g_fProviderEnabled, ebx
0x18002b172  jz      loc_18002B079
0x18002b178  mov     ecx, 1000000h
0x18002b17d  test    cs:g_ulTraceFlags, rcx
0x18002b184  jz      loc_18002B079
0x18002b18a  mov     r8, rdi
0x18002b18d  lea     rdx, aLdapaddtopendi; "LdapAddToPendingList couldn't bump for "...
0x18002b194  call    LDAPClientPrint
0x18002b199  jmp     loc_18002B079
```
