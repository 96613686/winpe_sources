# IERegGetValueInternal(uint,ulong *,void *,ulong *,ulong *,ushort const *,ushort const *)

- ea: `0x1800363e4`
- end: `0x1800366c9`
- name: `?IERegGetValueInternal@@YAJIPEAKPEAX00PEBG2@Z`
- size: `741`
- prototype: `int(unsigned int, unsigned int *, void *, unsigned int *, unsigned int *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180036394`

## callees

- `0x180003400`
- `0x18001018c`
- `0x180012550`
- `0x180013042`
- `0x180013066`
- `0x1800363e4`
- `0x1800368ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003658c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003658c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003657e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003657e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003653c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003653c`

## pseudocode

```c
__int64 __fastcall IERegGetValueInternal(
        unsigned int a1,
        unsigned int *a2,
        BYTE *a3,
        unsigned int *a4,
        unsigned int *a5,
        const unsigned __int16 *lpSubKey,
        const unsigned __int16 *a7)
{
  const WCHAR *v8; // r12
  __int64 v11; // rsi
  bool v13; // cl
  __int64 v14; // r8
  int i; // r14d
  int v16; // eax
  HKEY v17; // rcx
  DWORD v18; // eax
  LSTATUS v19; // r12d
  unsigned int v20; // ecx
  DWORD v21; // eax
  __int64 v22; // rcx
  rsize_t v23; // rdx
  __int16 *v24; // r8
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  BOOL v27; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v29; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpValueName; // [rsp+50h] [rbp-B0h]
  __int128 v31; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[22]; // [rsp+70h] [rbp-90h] BYREF
  char v33[490]; // [rsp+86h] [rbp-7Ah] BYREF

  v8 = lpSubKey;
  v29 = lpSubKey;
  lpValueName = a7;
  v11 = a1;
  IERegInit();
  if ( a3 && !a4 )
    return 2147747586LL;
  v31 = *(_OWORD *)L"Software\\Policies\\";
  *(_OWORD *)v32 = *(_OWORD *)L"\\Policies\\";
  *(_QWORD *)&v32[14] = *(_QWORD *)L"es\\";
  memset_0(v33, 0, 0x1E2u);
  v13 = (int)StringCchCopyW((unsigned __int16 *)&v32[20], 0xF2u, lpSubKey) >= 0;
  v27 = v13;
  for ( i = 0; i < 5; ++i )
  {
    v16 = 1;
    if ( i <= 1 && v13 )
      v16 = IsPolicyKeyPresentW(&v31, i != 0, v14, _ImageBase);
    v14 = i;
    if ( (dword_18004A880[i] & dword_180039054[10 * v11]) == dword_18004A880[i] )
    {
      v17 = (HKEY)qword_180059B60[i];
      if ( v17 )
      {
        if ( v16 )
        {
          hKey = 0;
          if ( !RegOpenKeyExW(v17, v8, 0, 0x20019u, &hKey) )
          {
            Type = 0;
            if ( a4 )
              v18 = *a4;
            else
              v18 = 0;
            cbData = v18;
            v19 = RegQueryValueExW(hKey, lpValueName, 0, &Type, a3, &cbData);
            RegCloseKey(hKey);
            if ( v19 && v19 != 234 )
            {
              v8 = v29;
            }
            else
            {
              v20 = dword_180039040[10 * v11];
              if ( v20 == Type )
              {
                v21 = cbData;
                if ( cbData )
                {
                  if ( a2 )
                    *a2 = v20;
                  if ( a5 )
                    *a5 = i;
                  if ( a4 )
                    *a4 = v21;
                  return v19 != 0 ? 0x80040702 : 0;
                }
              }
              v8 = v29;
            }
          }
        }
      }
    }
    v13 = v27;
  }
  if ( (dword_180039054[10 * v11] & 0x10) != 0 )
  {
    v22 = 40 * v11 + 233536;
    if ( a2 )
      *a2 = *(_DWORD *)((char *)_ImageBase + v22);
    if ( a5 )
      *a5 = 5;
    if ( a3 )
    {
      v23 = (unsigned int)dword_180039050[10 * v11];
      if ( *a4 < (unsigned int)v23 )
      {
        *a4 = v23;
        return 2147747586LL;
      }
      v24 = &_ImageBase[20 * v11 + 116772];
      if ( *(_DWORD *)((char *)_ImageBase + v22) != 4 )
        v24 = *(__int16 **)v24;
      memcpy_s(a3, *a4, v24, v23);
    }
    else if ( !a4 )
    {
      return 0;
    }
    *a4 = dword_180039050[10 * v11];
    return 0;
  }
  if ( a5 )
    *a5 = 6;
  return 2147747584LL;
}

```

## disassembly

```asm
0x1800363e4  push    rbp
0x1800363e6  push    rbx
0x1800363e7  push    rsi
0x1800363e8  push    rdi
0x1800363e9  push    r12
0x1800363eb  push    r13
0x1800363ed  push    r14
0x1800363ef  push    r15
0x1800363f1  lea     rbp, [rsp-188h]
0x1800363f9  sub     rsp, 288h
0x180036400  mov     rax, cs:__security_cookie
0x180036407  xor     rax, rsp
0x18003640a  mov     [rbp+1C0h+var_50], rax
0x180036411  mov     rax, [rbp+1C0h+arg_30]
0x180036418  mov     rbx, r9
0x18003641b  mov     r12, [rbp+1C0h+lpSubKey]
0x180036422  mov     r13, r8
0x180036425  mov     rdi, [rbp+1C0h+arg_20]
0x18003642c  mov     r15, rdx
0x18003642f  mov     [rsp+2C0h+var_278], r12
0x180036434  mov     [rsp+2C0h+lpValueName], rax
0x180036439  mov     esi, ecx
0x18003643b  call    IERegInit
0x180036440  test    r13, r13
0x180036443  jz      short loc_180036454
0x180036445  test    rbx, rbx
0x180036448  jnz     short loc_180036454
0x18003644a  mov     eax, 80040702h
0x18003644f  jmp     loc_1800366A6
0x180036454  movups  xmm0, xmmword ptr cs:aSoftwarePolici_2; "Software\\Policies\\"
0x18003645b  xor     edx, edx; Val
0x18003645d  mov     r8d, 1E2h; Size
0x180036463  movups  xmm1, xmmword ptr cs:aSoftwarePolici_2+10h; "\\Policies\\"
0x18003646a  lea     rcx, [rbp+1C0h+var_23A]; void *
0x18003646e  movaps  [rsp+2C0h+var_260], xmm0
0x180036473  movsd   xmm0, qword ptr cs:aSoftwarePolici_2+1Eh; "es\\"
0x18003647b  movaps  [rsp+2C0h+var_250], xmm1
0x180036480  movsd   qword ptr [rsp+2C0h+var_250+0Eh], xmm0
0x180036486  call    memset_0
0x18003648b  mov     r8, r12; unsigned __int16 *
0x18003648e  lea     rcx, [rbp+1C0h+var_23C]; unsigned __int16 *
0x180036492  mov     edx, 0F2h; unsigned __int64
0x180036497  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003649c  mov     ecx, eax
0x18003649e  lea     r9, __ImageBase
0x1800364a5  shr     ecx, 1Fh
0x1800364a8  xor     cl, 1
0x1800364ab  mov     [rsp+2C0h+var_288], ecx
0x1800364af  xor     r14d, r14d
0x1800364b2  cmp     r14d, 5
0x1800364b6  jge     loc_18003660A
0x1800364bc  mov     eax, 1
0x1800364c1  cmp     r14d, eax
0x1800364c4  jg      short loc_1800364E3
0x1800364c6  xor     edx, edx
0x1800364c8  test    r14d, r14d
0x1800364cb  setnz   dl
0x1800364ce  test    cl, cl
0x1800364d0  jz      short loc_1800364E3
0x1800364d2  lea     rcx, [rsp+2C0h+var_260]
0x1800364d7  call    IsPolicyKeyPresentW
0x1800364dc  lea     r9, __ImageBase
0x1800364e3  movsxd  r8, r14d
0x1800364e6  lea     rcx, [rsi+rsi*4]
0x1800364ea  mov     ecx, ds:rva dword_180039054[r9+rcx*8]
0x1800364f2  mov     edx, ds:rva dword_18004A880[r9+r8*4]
0x1800364fa  and     ecx, edx
0x1800364fc  cmp     ecx, edx
0x1800364fe  jnz     loc_1800365D4
0x180036504  mov     rcx, rva qword_180059B60[r9+r8*8]; hKey
0x18003650c  test    rcx, rcx
0x18003650f  jz      loc_1800365D4
0x180036515  test    eax, eax
0x180036517  jz      loc_1800365D4
0x18003651d  lea     rax, [rsp+2C0h+hKey]
0x180036522  mov     [rsp+2C0h+hKey], 0
0x18003652b  mov     r9d, 20019h; samDesired
0x180036531  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180036536  xor     r8d, r8d; ulOptions
0x180036539  mov     rdx, r12; lpSubKey
0x18003653c  call    cs:__imp_RegOpenKeyExW
0x180036542  test    eax, eax
0x180036544  jnz     loc_1800365CD
0x18003654a  mov     [rsp+2C0h+Type], eax
0x18003654e  test    rbx, rbx
0x180036551  jz      short loc_180036557
0x180036553  mov     eax, [rbx]
0x180036555  jmp     short loc_180036559
0x180036557  xor     eax, eax
0x180036559  mov     rdx, [rsp+2C0h+lpValueName]; lpValueName
0x18003655e  lea     r9, [rsp+2C0h+Type]; lpType
0x180036563  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180036568  xor     r8d, r8d; lpReserved
0x18003656b  mov     [rsp+2C0h+cbData], eax
0x18003656f  lea     rax, [rsp+2C0h+cbData]
0x180036574  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180036579  mov     [rsp+2C0h+phkResult], r13; lpData
0x18003657e  call    cs:__imp_RegQueryValueExW
0x180036584  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180036589  mov     r12d, eax
0x18003658c  call    cs:__imp_RegCloseKey
0x180036592  test    r12d, r12d
0x180036595  jz      short loc_1800365A0
0x180036597  cmp     r12d, 0EAh
0x18003659e  jnz     short loc_1800365C8
0x1800365a0  lea     rcx, [rsi+rsi*4]
0x1800365a4  lea     r9, __ImageBase
0x1800365ab  mov     ecx, ds:rva dword_180039040[r9+rcx*8]
0x1800365b3  cmp     ecx, [rsp+2C0h+Type]
0x1800365b7  jnz     short loc_1800365C1
0x1800365b9  mov     eax, [rsp+2C0h+cbData]
0x1800365bd  test    eax, eax
0x1800365bf  jnz     short loc_1800365E0
0x1800365c1  mov     r12, [rsp+2C0h+var_278]
0x1800365c6  jmp     short loc_1800365D4
0x1800365c8  mov     r12, [rsp+2C0h+var_278]
0x1800365cd  lea     r9, __ImageBase
0x1800365d4  mov     ecx, [rsp+2C0h+var_288]
0x1800365d8  inc     r14d
0x1800365db  jmp     loc_1800364B2
0x1800365e0  test    r15, r15
0x1800365e3  jz      short loc_1800365E8
0x1800365e5  mov     [r15], ecx
0x1800365e8  test    rdi, rdi
0x1800365eb  jz      short loc_1800365F0
0x1800365ed  mov     [rdi], r14d
0x1800365f0  test    rbx, rbx
0x1800365f3  jz      short loc_1800365F7
0x1800365f5  mov     [rbx], eax
0x1800365f7  xor     eax, eax
0x1800365f9  sub     eax, r12d
0x1800365fc  neg     eax
0x1800365fe  sbb     eax, eax
0x180036600  and     eax, 80040702h
0x180036605  jmp     loc_1800366A6
0x18003660a  lea     rdx, [rsi+rsi*4]
0x18003660e  test    byte ptr ds:rva dword_180039054[r9+rdx*8], 10h
0x180036617  jz      short loc_180036696
0x180036619  lea     rcx, ds:39040h[rdx*8]
0x180036621  test    r15, r15
0x180036624  jz      short loc_18003662D
0x180036626  mov     eax, [rcx+r9]
0x18003662a  mov     [r15], eax
0x18003662d  test    rdi, rdi
0x180036630  jz      short loc_180036638
0x180036632  mov     dword ptr [rdi], 5
0x180036638  test    r13, r13
0x18003663b  jz      short loc_18003667F
0x18003663d  mov     edx, ds:rva dword_180039050[r9+rdx*8]
0x180036645  cmp     [rbx], edx
0x180036647  jb      short loc_180036678
0x180036649  lea     rax, [rsi+rsi*4]
0x18003664d  lea     r8, ds:39048h[rax*8]
0x180036655  add     r8, r9
0x180036658  cmp     dword ptr [rcx+r9], 4
0x18003665d  jz      short loc_180036662
0x18003665f  mov     r8, [r8]; Source
0x180036662  mov     r9, rdx; SourceSize
0x180036665  mov     rcx, r13; Destination
0x180036668  mov     edx, [rbx]; DestinationSize
0x18003666a  call    memcpy_s
0x18003666f  lea     r9, __ImageBase
0x180036676  jmp     short loc_180036684
0x180036678  mov     [rbx], edx
0x18003667a  jmp     loc_18003644A
0x18003667f  test    rbx, rbx
0x180036682  jz      short loc_180036692
0x180036684  lea     rax, [rsi+rsi*4]
0x180036688  mov     eax, ds:rva dword_180039050[r9+rax*8]
0x180036690  mov     [rbx], eax
0x180036692  xor     eax, eax
0x180036694  jmp     short loc_1800366A6
0x180036696  test    rdi, rdi
0x180036699  jz      short loc_1800366A1
0x18003669b  mov     dword ptr [rdi], 6
0x1800366a1  mov     eax, 80040700h
0x1800366a6  mov     rcx, [rbp+1C0h+var_50]
0x1800366ad  xor     rcx, rsp; StackCookie
0x1800366b0  call    __security_check_cookie
0x1800366b5  add     rsp, 288h
0x1800366bc  pop     r15
0x1800366be  pop     r14
0x1800366c0  pop     r13
0x1800366c2  pop     r12
0x1800366c4  pop     rdi
0x1800366c5  pop     rsi
0x1800366c6  pop     rbx
0x1800366c7  pop     rbp
0x1800366c8  retn
```
