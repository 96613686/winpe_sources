# AuthPortMgrDeleteAll

- ea: `0x18007bf58`
- end: `0x18007c07f`
- name: `AuthPortMgrDeleteAll`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18007a0d4`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007bf58`
- `0x18007c15c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007c034`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007c034`
- `MobileNetworking!ReleaseWriteLock` at `0x18007c01a`
- `MobileNetworking!ReleaseWriteLock` at `0x18007c01a`
- `MobileNetworking!AcquireWriteLock` at `0x18007bfab`
- `MobileNetworking!AcquireWriteLock` at `0x18007bfab`

## string_xrefs

- `0x18007bf96`: `AuthPortMgrDeleteAll`
- `0x18007c005`: `AuthPortMgrDeleteAll`

## pseudocode

```c
void AuthPortMgrDeleteAll()
{
  __int64 v0; // rcx
  _QWORD *v1; // rdx
  __int64 v2; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids);
  AcquireWriteLock(&g_WcnOneXInfo, qword_1800BB520, "AuthPortMgrDeleteAll", 280);
  while ( 1 )
  {
    v2 = qword_1800BB510;
    if ( (__int64 *)qword_1800BB510 == &qword_1800BB510 )
      break;
    v0 = *(_QWORD *)qword_1800BB510;
    if ( *(_QWORD *)(*(_QWORD *)qword_1800BB510 + 8LL) != qword_1800BB510
      || (v1 = *(_QWORD **)(qword_1800BB510 + 8), *v1 != qword_1800BB510) )
    {
      __fastfail(3u);
    }
    *v1 = v0;
    *(_QWORD *)(v0 + 8) = v1;
    *(_DWORD *)(v2 + 128) &= 0x3FFFFFFFu;
    *(_DWORD *)(v2 + 128) |= 0x40000000u;
    AuthPortMgrDereferencePort(v2);
  }
  ReleaseWriteLock(&g_WcnOneXInfo, qword_1800BB520, "AuthPortMgrDeleteAll", 299);
  while ( HIDWORD(qword_1800BB588) )
    Sleep(0x64u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, 0);
}

```

## disassembly

```asm
0x18007bf58  mov     [rsp+arg_0], rbx
0x18007bf5d  push    rdi
0x18007bf5e  sub     rsp, 20h
0x18007bf62  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bf69  lea     rbx, WPP_GLOBAL_Control
0x18007bf70  cmp     rcx, rbx
0x18007bf73  jz      short loc_18007BF90
0x18007bf75  test    byte ptr [rcx+1Ch], 1
0x18007bf79  jz      short loc_18007BF90
0x18007bf7b  mov     rcx, [rcx+10h]
0x18007bf7f  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007bf86  mov     edx, 1Fh
0x18007bf8b  call    WPP_SF_
0x18007bf90  mov     r9d, 118h
0x18007bf96  lea     r8, aAuthportmgrdel; "AuthPortMgrDeleteAll"
0x18007bf9d  lea     rdx, qword_1800BB520
0x18007bfa4  lea     rcx, g_WcnOneXInfo
0x18007bfab  call    cs:__imp_AcquireWriteLock
0x18007bfb2  nop     dword ptr [rax+rax+00h]
0x18007bfb7  lea     rdi, qword_1800BB510
0x18007bfbe  jmp     short loc_18007BFF3
0x18007bfc0  mov     rcx, [rax]
0x18007bfc3  cmp     [rcx+8], rax
0x18007bfc7  jnz     short loc_18007C028
0x18007bfc9  mov     rdx, [rax+8]
0x18007bfcd  cmp     [rdx], rax
0x18007bfd0  jnz     short loc_18007C028
0x18007bfd2  mov     [rdx], rcx
0x18007bfd5  mov     [rcx+8], rdx
0x18007bfd9  mov     rcx, rax
0x18007bfdc  and     dword ptr [rax+80h], 3FFFFFFFh
0x18007bfe6  bts     dword ptr [rax+80h], 1Eh
0x18007bfee  call    AuthPortMgrDereferencePort
0x18007bff3  mov     rax, cs:qword_1800BB510
0x18007bffa  cmp     rax, rdi
0x18007bffd  jnz     short loc_18007BFC0
0x18007bfff  mov     r9d, 12Bh
0x18007c005  lea     r8, aAuthportmgrdel; "AuthPortMgrDeleteAll"
0x18007c00c  lea     rdx, qword_1800BB520
0x18007c013  lea     rcx, g_WcnOneXInfo
0x18007c01a  call    cs:__imp_ReleaseWriteLock
0x18007c021  nop     dword ptr [rax+rax+00h]
0x18007c026  jmp     short loc_18007C040
0x18007c028  mov     ecx, 3
0x18007c02d  int     29h; Win8: RtlFailFast(ecx)
0x18007c02f  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18007c034  call    cs:__imp_Sleep
0x18007c03b  nop     dword ptr [rax+rax+00h]
0x18007c040  cmp     dword ptr cs:qword_1800BB588+4, 0
0x18007c047  jnz     short loc_18007C02F
0x18007c049  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c050  cmp     rcx, rbx
0x18007c053  jz      short loc_18007C073
0x18007c055  test    byte ptr [rcx+1Ch], 1
0x18007c059  jz      short loc_18007C073
0x18007c05b  mov     rcx, [rcx+10h]
0x18007c05f  lea     r8, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007c066  mov     edx, 20h ; ' '
0x18007c06b  xor     r9d, r9d
0x18007c06e  call    WPP_SF_d
0x18007c073  mov     rbx, [rsp+28h+arg_0]
0x18007c078  add     rsp, 20h
0x18007c07c  pop     rdi
0x18007c07d  retn
```
