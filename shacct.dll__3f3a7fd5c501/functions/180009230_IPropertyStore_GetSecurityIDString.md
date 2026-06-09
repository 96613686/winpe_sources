# IPropertyStore_GetSecurityIDString

- ea: `0x180009230`
- end: `0x1800092da`
- name: `IPropertyStore_GetSecurityIDString`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009c10`

## callees

- `0x180009230`
- `0x18000bcc0`
- `0x180017010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x1800092a6`
- `SHCORE!SHStrDupW` at `0x1800092a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800092c7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800092c7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009294`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009294`

## pseudocode

```c
__int64 __fastcall IPropertyStore_GetSecurityIDString(__int64 *a1, WCHAR *a2, LPWSTR *a3)
{
  __int64 v3; // rax
  __int64 result; // rax
  unsigned int Error; // edi
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  PSID Sid; // [rsp+30h] [rbp-18h]
  LPWSTR StringSid; // [rsp+58h] [rbp+10h] BYREF

  StringSid = a2;
  *a3 = 0;
  Sid = 0;
  v3 = *a1;
  *(_OWORD *)pvar = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, __int128 *, PROPVARIANT *))(v3 + 40))(a1, &PKEY_SAM_SecurityID, pvar);
  if ( (int)result >= 0 )
  {
    Error = -2147467259;
    if ( LOWORD(pvar[0]) == 65 )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(Sid, &StringSid) )
      {
        Error = SHStrDupW(StringSid, a3);
        LocalFree(StringSid);
      }
      else
      {
        Error = ResultFromKnownLastError();
      }
    }
    PropVariantClear(pvar);
    return Error;
  }
  return result;
}

```

## disassembly

```asm
0x180009230  mov     [rsp+StringSid], rdx
0x180009235  push    rbx
0x180009236  sub     rsp, 40h
0x18000923a  xor     eax, eax
0x18000923c  mov     qword ptr [r8], 0
0x180009243  mov     [rsp+48h+Sid], rax
0x180009248  lea     rdx, PKEY_SAM_SecurityID
0x18000924f  mov     rax, [rcx]
0x180009252  mov     rbx, r8
0x180009255  xorps   xmm0, xmm0
0x180009258  lea     r8, [rsp+48h+pvar]
0x18000925d  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180009262  mov     rax, [rax+28h]
0x180009266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000926b  test    eax, eax
0x18000926d  js      short loc_1800092D4
0x18000926f  cmp     word ptr [rsp+48h+pvar], 41h ; 'A'
0x180009275  mov     [rsp+48h+arg_0], rdi
0x18000927a  mov     edi, 80004005h
0x18000927f  jnz     short loc_1800092C2
0x180009281  mov     rcx, [rsp+48h+Sid]; Sid
0x180009286  lea     rdx, [rsp+48h+StringSid]; StringSid
0x18000928b  mov     [rsp+48h+StringSid], 0
0x180009294  call    cs:__imp_ConvertSidToStringSidW
0x18000929a  test    eax, eax
0x18000929c  jz      short loc_1800092BB
0x18000929e  mov     rcx, [rsp+48h+StringSid]; psz
0x1800092a3  mov     rdx, rbx; ppwsz
0x1800092a6  call    cs:__imp_SHStrDupW
0x1800092ac  mov     rcx, [rsp+48h+StringSid]; hMem
0x1800092b1  mov     edi, eax
0x1800092b3  call    cs:__imp_LocalFree
0x1800092b9  jmp     short loc_1800092C2
0x1800092bb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800092c0  mov     edi, eax
0x1800092c2  lea     rcx, [rsp+48h+pvar]; pvar
0x1800092c7  call    cs:__imp_PropVariantClear
0x1800092cd  mov     eax, edi
0x1800092cf  mov     rdi, [rsp+48h+arg_0]
0x1800092d4  add     rsp, 40h
0x1800092d8  pop     rbx
0x1800092d9  retn
```
