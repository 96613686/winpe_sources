# GetTokenSid

- ea: `0x140797744`
- end: `0x1407978bc`
- name: `GetTokenSid`
- size: `376`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1407980f8`

## callees

- `0x1404828e0`
- `0x140797744`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140797879`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140797879`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1407977b1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1407977b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1407977c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140797808`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1407977c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140797808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140797798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140797798`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14079788d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14079788d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14079783e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14079783e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14079782c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14079782c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14079785f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14079785f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140797819`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140797819`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140797788`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1407977f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140797788`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1407977f3`

## pseudocode

```c
char __fastcall GetTokenSid(HANDLE TokenHandle, _QWORD *a2)
{
  char v4; // bl
  PSID *v5; // rsi
  void *v6; // rdi
  DWORD v7; // ecx
  DWORD LengthSid; // ebp
  HLOCAL v9; // rax
  size_t Size; // [rsp+30h] [rbp-28h] BYREF

  LODWORD(Size) = 0;
  v4 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenOwner, 0, 0, (PDWORD)&Size) && GetLastError() != 122 )
    return v4;
  v5 = (PSID *)malloc((unsigned int)Size);
  if ( !v5 )
  {
    SetLastError(0xEu);
    return v4;
  }
  v6 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenOwner, v5, Size, (PDWORD)&Size) || !IsValidSid(*v5) )
    goto LABEL_6;
  LengthSid = GetLengthSid(*v5);
  v9 = LocalAlloc(0, LengthSid);
  v6 = v9;
  if ( !v9 )
  {
    v7 = 14;
    goto LABEL_7;
  }
  if ( !CopySid(LengthSid, v9, *v5) )
  {
LABEL_6:
    v7 = 87;
LABEL_7:
    SetLastError(v7);
    goto LABEL_13;
  }
  *a2 = v6;
  v4 = 1;
  v6 = 0;
LABEL_13:
  free(v5);
  if ( v6 )
    LocalFree(v6);
  return v4;
}

```

## disassembly

```asm
0x140797744  mov     r11, rsp
0x140797747  mov     [r11+18h], rbx
0x14079774b  mov     [r11+20h], rbp
0x14079774f  push    rsi
0x140797750  push    rdi
0x140797751  push    r14
0x140797753  sub     rsp, 40h
0x140797757  mov     rax, cs:__security_cookie
0x14079775e  xor     rax, rsp
0x140797761  mov     [rsp+58h+var_20], rax
0x140797766  xor     r9d, r9d; TokenInformationLength
0x140797769  mov     dword ptr [rsp+58h+Size], 0
0x140797771  mov     r14, rdx
0x140797774  lea     rax, [r11-28h]
0x140797778  xor     r8d, r8d; TokenInformation
0x14079777b  mov     [r11-38h], rax
0x14079777f  mov     rbp, rcx
0x140797782  xor     bl, bl
0x140797784  lea     edx, [r9+4]; TokenInformationClass
0x140797788  call    cs:__imp_GetTokenInformation
0x14079778f  nop     dword ptr [rax+rax+00h]
0x140797794  test    eax, eax
0x140797796  jnz     short loc_1407977AD
0x140797798  call    cs:__imp_GetLastError
0x14079779f  nop     dword ptr [rax+rax+00h]
0x1407977a4  cmp     eax, 7Ah ; 'z'
0x1407977a7  jnz     loc_140797899
0x1407977ad  mov     ecx, dword ptr [rsp+58h+Size]; Size
0x1407977b1  call    cs:__imp_malloc
0x1407977b8  nop     dword ptr [rax+rax+00h]
0x1407977bd  mov     rsi, rax
0x1407977c0  test    rax, rax
0x1407977c3  jnz     short loc_1407977D9
0x1407977c5  lea     ecx, [rax+0Eh]; dwErrCode
0x1407977c8  call    cs:__imp_SetLastError
0x1407977cf  nop     dword ptr [rax+rax+00h]
0x1407977d4  jmp     loc_140797899
0x1407977d9  mov     r9d, dword ptr [rsp+58h+Size]; TokenInformationLength
0x1407977de  lea     rax, [rsp+58h+Size]
0x1407977e3  xor     edi, edi
0x1407977e5  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1407977ea  mov     r8, rsi; TokenInformation
0x1407977ed  mov     rcx, rbp; TokenHandle
0x1407977f0  lea     edx, [rdi+4]; TokenInformationClass
0x1407977f3  call    cs:__imp_GetTokenInformation
0x1407977fa  nop     dword ptr [rax+rax+00h]
0x1407977ff  test    eax, eax
0x140797801  jnz     short loc_140797816
0x140797803  mov     ecx, 57h ; 'W'; dwErrCode
0x140797808  call    cs:__imp_SetLastError
0x14079780f  nop     dword ptr [rax+rax+00h]
0x140797814  jmp     short loc_140797876
0x140797816  mov     rcx, [rsi]; pSid
0x140797819  call    cs:__imp_IsValidSid
0x140797820  nop     dword ptr [rax+rax+00h]
0x140797825  test    eax, eax
0x140797827  jz      short loc_140797803
0x140797829  mov     rcx, [rsi]; pSid
0x14079782c  call    cs:__imp_GetLengthSid
0x140797833  nop     dword ptr [rax+rax+00h]
0x140797838  mov     edx, eax; uBytes
0x14079783a  xor     ecx, ecx; uFlags
0x14079783c  mov     ebp, eax
0x14079783e  call    cs:__imp_LocalAlloc
0x140797845  nop     dword ptr [rax+rax+00h]
0x14079784a  mov     rdi, rax
0x14079784d  test    rax, rax
0x140797850  jnz     short loc_140797857
0x140797852  lea     ecx, [rax+0Eh]
0x140797855  jmp     short loc_140797808
0x140797857  mov     r8, [rsi]; pSourceSid
0x14079785a  mov     rdx, rdi; pDestinationSid
0x14079785d  mov     ecx, ebp; nDestinationSidLength
0x14079785f  call    cs:__imp_CopySid
0x140797866  nop     dword ptr [rax+rax+00h]
0x14079786b  test    eax, eax
0x14079786d  jz      short loc_140797803
0x14079786f  mov     [r14], rdi
0x140797872  mov     bl, 1
0x140797874  xor     edi, edi
0x140797876  mov     rcx, rsi; Block
0x140797879  call    cs:__imp_free
0x140797880  nop     dword ptr [rax+rax+00h]
0x140797885  test    rdi, rdi
0x140797888  jz      short loc_140797899
0x14079788a  mov     rcx, rdi; hMem
0x14079788d  call    cs:__imp_LocalFree
0x140797894  nop     dword ptr [rax+rax+00h]
0x140797899  mov     al, bl
0x14079789b  mov     rcx, [rsp+58h+var_20]
0x1407978a0  xor     rcx, rsp; StackCookie
0x1407978a3  call    __security_check_cookie
0x1407978a8  mov     rbx, [rsp+58h+arg_10]
0x1407978ad  mov     rbp, [rsp+58h+arg_18]
0x1407978b2  add     rsp, 40h
0x1407978b6  pop     r14
0x1407978b8  pop     rdi
0x1407978b9  pop     rsi
0x1407978ba  retn
```
