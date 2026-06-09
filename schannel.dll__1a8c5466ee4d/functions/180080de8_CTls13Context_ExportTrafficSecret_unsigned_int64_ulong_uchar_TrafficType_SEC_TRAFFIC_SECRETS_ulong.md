# CTls13Context::ExportTrafficSecret(unsigned __int64,ulong,uchar,TrafficType,_SEC_TRAFFIC_SECRETS *,ulong)

- ea: `0x180080de8`
- end: `0x180080f3e`
- name: `?ExportTrafficSecret@CTls13Context@@AEAAK_KKEW4TrafficType@@PEAU_SEC_TRAFFIC_SECRETS@@K@Z`
- size: `342`
- prototype: `unsigned int __high(unsigned __int64, unsigned int, unsigned __int8, enum TrafficType, struct _SEC_TRAFFIC_SECRETS *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800818e4`

## callees

- `0x180080ce8`
- `0x180080de8`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180080e97`
- `bcrypt!BCryptGetProperty` at `0x180080e97`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180080f1b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180080f1b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180080e64`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180080e64`

## pseudocode

```c
__int64 __fastcall CTls13Context::ExportTrafficSecret(
        __int64 a1,
        unsigned __int64 a2,
        int a3,
        char a4,
        unsigned __int8 a5,
        __int64 a6,
        ULONG a7)
{
  __int64 v10; // rdi
  unsigned int Property; // ebx
  unsigned __int64 v12; // r8
  BCRYPT_HANDLE hObject; // [rsp+30h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 2148074333LL;
  if ( !a3 )
    return 2148074333LL;
  if ( !a7 )
    return 2148074333LL;
  if ( !a5 )
    return 2148074333LL;
  v10 = a6;
  if ( !a6 )
    return 2148074333LL;
  pcbResult = 0;
  hObject = 0;
  Property = BCryptOpenAlgorithmProvider(&hObject, (LPCWSTR)(a6 + 256), 0, 0);
  if ( !Property )
  {
    Property = BCryptGetProperty(hObject, L"HashDigestLength", (PUCHAR)&pcbResult, 4u, &pcbResult, 0);
    if ( !Property )
    {
      if ( pcbResult <= a7 )
      {
        v12 = 0;
        if ( a5 == 2 )
        {
          v12 = *(_QWORD *)((a4 != 0 ? 8 : 0) + a1 + 56);
        }
        else if ( a5 == 3 )
        {
          v12 = *(_QWORD *)((a4 != 0 ? 8 : 0) + a1 + 80);
        }
        Property = CTls13Context::ExportRawSecretBytes(
                     (CTls13Context *)((unsigned int)a5 - 2),
                     a2,
                     v12,
                     (unsigned __int8 *)(v10 + 398),
                     pcbResult);
        if ( !Property )
          *(_WORD *)(v10 + 396) = pcbResult;
      }
      else
      {
        Property = -2146893052;
      }
    }
  }
  if ( hObject )
    BCryptCloseAlgorithmProvider(hObject, 0);
  return Property;
}

```

## disassembly

```asm
0x180080de8  mov     rax, rsp
0x180080deb  mov     [rax+8], rbx
0x180080def  mov     [rax+18h], rsi
0x180080df3  push    rdi
0x180080df4  push    r12
0x180080df6  push    r15
0x180080df8  sub     rsp, 40h
0x180080dfc  mov     sil, r9b
0x180080dff  mov     r12, rdx
0x180080e02  mov     r15, rcx
0x180080e05  test    rdx, rdx
0x180080e08  jz      loc_180080F25
0x180080e0e  test    r8d, r8d
0x180080e11  jz      loc_180080F25
0x180080e17  cmp     [rsp+58h+arg_30], 0
0x180080e1f  jz      loc_180080F25
0x180080e25  cmp     [rsp+58h+arg_20], 0
0x180080e2d  jz      loc_180080F25
0x180080e33  mov     rdi, [rsp+58h+arg_28]
0x180080e3b  test    rdi, rdi
0x180080e3e  jz      loc_180080F25
0x180080e44  lea     rdx, [rdi+100h]; pszAlgId
0x180080e4b  mov     dword ptr [rax+10h], 0
0x180080e52  xor     r9d, r9d; dwFlags
0x180080e55  mov     qword ptr [rax-28h], 0
0x180080e5d  xor     r8d, r8d; pszImplementation
0x180080e60  lea     rcx, [rax-28h]; phAlgorithm
0x180080e64  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180080e6a  mov     ebx, eax
0x180080e6c  test    eax, eax
0x180080e6e  jnz     loc_180080F0F
0x180080e74  mov     rcx, [rsp+58h+hObject]; hObject
0x180080e79  lea     r9d, [rbx+4]; cbOutput
0x180080e7d  mov     [rsp+58h+dwFlags], eax; dwFlags
0x180080e81  lea     r8, [rsp+58h+arg_8]; pbOutput
0x180080e86  lea     rax, [rsp+58h+arg_8]
0x180080e8b  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180080e92  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180080e97  call    cs:__imp_BCryptGetProperty
0x180080e9d  mov     ebx, eax
0x180080e9f  test    eax, eax
0x180080ea1  jnz     short loc_180080F0F
0x180080ea3  mov     edx, [rsp+58h+arg_8]
0x180080ea7  cmp     edx, [rsp+58h+arg_30]
0x180080eae  jbe     short loc_180080EB7
0x180080eb0  mov     ebx, 80090304h
0x180080eb5  jmp     short loc_180080F0F
0x180080eb7  movzx   ecx, [rsp+58h+arg_20]
0x180080ebf  xor     r8d, r8d
0x180080ec2  sub     ecx, 2; this
0x180080ec5  jz      short loc_180080EDC
0x180080ec7  cmp     ecx, 1
0x180080eca  jnz     short loc_180080EEA
0x180080ecc  neg     sil
0x180080ecf  sbb     rax, rax
0x180080ed2  and     eax, 8
0x180080ed5  mov     r8, [rax+r15+50h]
0x180080eda  jmp     short loc_180080EEA
0x180080edc  neg     sil
0x180080edf  sbb     rax, rax
0x180080ee2  and     eax, 8
0x180080ee5  mov     r8, [rax+r15+38h]; unsigned __int64
0x180080eea  mov     dword ptr [rsp+58h+pcbResult], edx; unsigned int
0x180080eee  lea     r9, [rdi+18Eh]; unsigned __int8 *
0x180080ef5  mov     rdx, r12; unsigned __int64
0x180080ef8  call    ?ExportRawSecretBytes@CTls13Context@@AEAAK_K0PEAEK@Z; CTls13Context::ExportRawSecretBytes(unsigned __int64,unsigned __int64,uchar *,ulong)
0x180080efd  mov     ebx, eax
0x180080eff  test    eax, eax
0x180080f01  jnz     short loc_180080F0F
0x180080f03  movzx   eax, word ptr [rsp+58h+arg_8]
0x180080f08  mov     [rdi+18Ch], ax
0x180080f0f  mov     rcx, [rsp+58h+hObject]; hAlgorithm
0x180080f14  test    rcx, rcx
0x180080f17  jz      short loc_180080F21
0x180080f19  xor     edx, edx; dwFlags
0x180080f1b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180080f21  mov     eax, ebx
0x180080f23  jmp     short loc_180080F2A
0x180080f25  mov     eax, 8009035Dh
0x180080f2a  mov     rbx, [rsp+58h+arg_0]
0x180080f2f  mov     rsi, [rsp+58h+arg_10]
0x180080f34  add     rsp, 40h
0x180080f38  pop     r15
0x180080f3a  pop     r12
0x180080f3c  pop     rdi
0x180080f3d  retn
```
