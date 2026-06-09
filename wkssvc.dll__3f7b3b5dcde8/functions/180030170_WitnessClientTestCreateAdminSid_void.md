# WitnessClientTestCreateAdminSid(void)

- ea: `0x180030170`
- end: `0x18003021f`
- name: `?WitnessClientTestCreateAdminSid@@YAKXZ`
- size: `175`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030228`

## callees

- `0x18000b76c`
- `0x180022b7c`
- `0x180030170`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301d1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180030189`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800301c7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180030189`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800301c7`

## pseudocode

```c
__int64 WitnessClientTestCreateAdminSid(void)
{
  DWORD LastError; // ebx
  void *v1; // rax
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  LastError = 0;
  cbSid = 0;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, 0, &cbSid) )
  {
    if ( GetLastError() == 122 )
    {
      v1 = MemoryAlloc(cbSid);
      g_AdminSid = v1;
      if ( v1 )
      {
        if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v1, &cbSid) )
          LastError = GetLastError();
      }
      else
      {
        LastError = 1450;
      }
    }
    else
    {
      LastError = 31;
    }
  }
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
      10,
      WPP_928f46f8e8b33892db621c8a8e2317d7_Traceguids,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180030170  push    rbx
0x180030172  sub     rsp, 20h
0x180030176  xor     ebx, ebx
0x180030178  lea     r9, [rsp+28h+cbSid]; cbSid
0x18003017d  xor     r8d, r8d; pSid
0x180030180  mov     [rsp+28h+cbSid], ebx
0x180030184  xor     edx, edx; DomainSid
0x180030186  lea     ecx, [rbx+1Ah]; WellKnownSidType
0x180030189  call    cs:__imp_CreateWellKnownSid
0x18003018f  test    eax, eax
0x180030191  jnz     short loc_1800301E0
0x180030193  call    cs:__imp_GetLastError
0x180030199  cmp     eax, 7Ah ; 'z'
0x18003019c  jnz     short loc_1800301DB
0x18003019e  mov     ecx, [rsp+28h+cbSid]; unsigned __int64
0x1800301a2  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x1800301a7  mov     cs:?g_AdminSid@@3PEAXEA, rax; void * g_AdminSid
0x1800301ae  test    rax, rax
0x1800301b1  jnz     short loc_1800301BA
0x1800301b3  mov     ebx, 5AAh
0x1800301b8  jmp     short loc_1800301E0
0x1800301ba  xor     edx, edx; DomainSid
0x1800301bc  lea     r9, [rsp+28h+cbSid]; cbSid
0x1800301c1  mov     r8, rax; pSid
0x1800301c4  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800301c7  call    cs:__imp_CreateWellKnownSid
0x1800301cd  test    eax, eax
0x1800301cf  jnz     short loc_1800301E0
0x1800301d1  call    cs:__imp_GetLastError
0x1800301d7  mov     ebx, eax
0x1800301d9  jmp     short loc_1800301E0
0x1800301db  mov     ebx, 1Fh
0x1800301e0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800301e7  lea     rax, WPP_witness_GLOBAL_Control
0x1800301ee  cmp     rcx, rax
0x1800301f1  jz      short loc_180030217
0x1800301f3  test    byte ptr [rcx+1Ch], 1
0x1800301f7  jz      short loc_180030217
0x1800301f9  cmp     byte ptr [rcx+19h], 3
0x1800301fd  jb      short loc_180030217
0x1800301ff  mov     rcx, [rcx+10h]
0x180030203  lea     r8, WPP_928f46f8e8b33892db621c8a8e2317d7_Traceguids
0x18003020a  mov     edx, 0Ah
0x18003020f  mov     r9d, ebx
0x180030212  call    WPP_SF_d
0x180030217  mov     eax, ebx
0x180030219  add     rsp, 20h
0x18003021d  pop     rbx
0x18003021e  retn
```
