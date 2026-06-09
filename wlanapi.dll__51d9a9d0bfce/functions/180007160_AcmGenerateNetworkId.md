# AcmGenerateNetworkId

- ea: `0x180007160`
- end: `0x180007318`
- name: `AcmGenerateNetworkId`
- size: `440`
- prototype: `__int64 __fastcall(PUCHAR pbInput)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007160`
- `0x180007320`
- `0x180019a20`
- `0x18001a5bc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800071d6`
- `ntdll!RtlNtStatusToDosError` at `0x18000728c`
- `ntdll!RtlNtStatusToDosError` at `0x1800071d6`
- `ntdll!RtlNtStatusToDosError` at `0x18000728c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007284`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007284`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800071ce`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800071ce`

## pseudocode

```c
__int64 __fastcall AcmGenerateNetworkId(PUCHAR pbInput, __int64 a2, _OWORD *a3)
{
  __int64 v4; // rdi
  NTSTATUS v6; // eax
  ULONG v7; // eax
  BCRYPT_ALG_HANDLE v8; // rbx
  unsigned int v9; // esi
  bool v10; // zf
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  unsigned int ConnectionHashId; // eax
  NTSTATUS v14; // eax
  __int64 v16; // rcx
  char *v17; // rax
  __int64 v18; // rdx
  char *v19; // rcx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+20h] [rbp-2A8h] BYREF
  _BYTE v21[4]; // [rsp+30h] [rbp-298h] BYREF
  int v22; // [rsp+34h] [rbp-294h]
  char v23; // [rsp+38h] [rbp-290h] BYREF
  __int128 v24; // [rsp+238h] [rbp-90h]
  __int128 v25; // [rsp+248h] [rbp-80h]
  int v26; // [rsp+258h] [rbp-70h]
  int v27; // [rsp+25Ch] [rbp-6Ch]
  int v28; // [rsp+27Ch] [rbp-4Ch]

  phAlgorithm = 0;
  v4 = a2;
  if ( !pbInput || !a2 || !a3 )
    return 87;
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 8u);
  v7 = RtlNtStatusToDosError(v6);
  v8 = phAlgorithm;
  v9 = v7;
  if ( !v7 )
  {
    if ( phAlgorithm )
    {
      memset_0(v21, 0, 0x25Cu);
      v10 = (*(_BYTE *)(v4 + 620) & 2) == 0;
      v11 = *(_OWORD *)(v4 + 512);
      v12 = *(_OWORD *)(v4 + 528);
      v26 = *(_DWORD *)(v4 + 544);
      v24 = v11;
      v25 = v12;
      if ( v10 )
      {
        v27 = *(_DWORD *)(v4 + 548);
        v28 = *(_DWORD *)(v4 + 608);
        v22 = 1;
      }
      else
      {
        v16 = 2147483646;
        v17 = &v23;
        v18 = 256;
        do
        {
          if ( !v16 )
            break;
          if ( !*(_WORD *)v4 )
            break;
          *(_WORD *)v17 = *(_WORD *)v4;
          v4 += 2;
          v17 += 2;
          --v16;
          --v18;
        }
        while ( v18 );
        v19 = v17 - 2;
        if ( v18 )
          v19 = v17;
        *(_WORD *)v19 = 0;
        v22 = 0;
      }
      ConnectionHashId = AcmGenerateConnectionHashId(v8, pbInput, (__int64)v21, a3);
      v8 = phAlgorithm;
      v9 = ConnectionHashId;
    }
    else
    {
      v9 = 87;
    }
  }
  if ( v8 )
  {
    v14 = BCryptCloseAlgorithmProvider(v8, 0);
    RtlNtStatusToDosError(v14);
  }
  return v9;
}

```

## disassembly

```asm
0x180007160  push    rbp
0x180007162  push    rsi
0x180007163  push    rdi
0x180007164  push    r14
0x180007166  push    r15
0x180007168  sub     rsp, 2A0h
0x18000716f  mov     rax, cs:__security_cookie
0x180007176  xor     rax, rsp
0x180007179  mov     [rsp+2C8h+var_38], rax
0x180007181  xor     r15d, r15d
0x180007184  mov     rbp, r8
0x180007187  mov     [rsp+2C8h+phAlgorithm], r15
0x18000718c  mov     rdi, rdx
0x18000718f  mov     r14, rcx
0x180007192  test    rcx, rcx
0x180007195  jz      loc_1800072BB
0x18000719b  test    rdx, rdx
0x18000719e  jz      loc_1800072BB
0x1800071a4  test    r8, r8
0x1800071a7  jz      loc_1800072BB
0x1800071ad  mov     r9d, 8; dwFlags
0x1800071b3  mov     [rsp+2C8h+arg_18], rbx
0x1800071bb  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800071c2  lea     rdx, pszAlgId; "SHA256"
0x1800071c9  lea     rcx, [rsp+2C8h+phAlgorithm]; phAlgorithm
0x1800071ce  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800071d4  mov     ecx, eax; Status
0x1800071d6  call    cs:__imp_RtlNtStatusToDosError
0x1800071dc  mov     rbx, [rsp+2C8h+phAlgorithm]
0x1800071e1  mov     esi, eax
0x1800071e3  test    eax, eax
0x1800071e5  jnz     loc_18000727A
0x1800071eb  test    rbx, rbx
0x1800071ee  jz      loc_18000730E
0x1800071f4  xor     edx, edx; Val
0x1800071f6  lea     rcx, [rsp+2C8h+var_298]; void *
0x1800071fb  mov     r8d, 25Ch; Size
0x180007201  call    memset_0
0x180007206  test    byte ptr [rdi+26Ch], 2
0x18000720d  movups  xmm0, xmmword ptr [rdi+200h]
0x180007214  mov     eax, [rdi+220h]
0x18000721a  movups  xmm1, xmmword ptr [rdi+210h]
0x180007221  mov     [rsp+2C8h+var_70], eax
0x180007228  movups  [rsp+2C8h+var_90], xmm0
0x180007230  movups  [rsp+2C8h+var_80], xmm1
0x180007238  jnz     loc_1800072C2
0x18000723e  mov     eax, [rdi+224h]
0x180007244  mov     [rsp+2C8h+var_6C], eax
0x18000724b  mov     eax, [rdi+260h]
0x180007251  mov     [rsp+2C8h+var_4C], eax
0x180007258  mov     [rsp+2C8h+var_294], 1
0x180007260  mov     r9, rbp
0x180007263  lea     r8, [rsp+2C8h+var_298]
0x180007268  mov     rdx, r14; pbInput
0x18000726b  mov     rcx, rbx; hAlgorithm
0x18000726e  call    AcmGenerateConnectionHashId
0x180007273  mov     rbx, [rsp+2C8h+phAlgorithm]
0x180007278  mov     esi, eax
0x18000727a  test    rbx, rbx
0x18000727d  jz      short loc_180007292
0x18000727f  xor     edx, edx; dwFlags
0x180007281  mov     rcx, rbx; hAlgorithm
0x180007284  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000728a  mov     ecx, eax; Status
0x18000728c  call    cs:__imp_RtlNtStatusToDosError
0x180007292  mov     rbx, [rsp+2C8h+arg_18]
0x18000729a  mov     eax, esi
0x18000729c  mov     rcx, [rsp+2C8h+var_38]
0x1800072a4  xor     rcx, rsp; StackCookie
0x1800072a7  call    __security_check_cookie
0x1800072ac  add     rsp, 2A0h
0x1800072b3  pop     r15
0x1800072b5  pop     r14
0x1800072b7  pop     rdi
0x1800072b8  pop     rsi
0x1800072b9  pop     rbp
0x1800072ba  retn
0x1800072bb  mov     eax, 57h ; 'W'
0x1800072c0  jmp     short loc_18000729C
0x1800072c2  mov     ecx, 7FFFFFFEh
0x1800072c7  lea     rax, [rsp+2C8h+var_290]
0x1800072cc  mov     edx, 100h
0x1800072d1  test    rcx, rcx
0x1800072d4  jz      short loc_1800072F5
0x1800072d6  movzx   r8d, word ptr [rdi]
0x1800072da  test    r8w, r8w
0x1800072de  jz      short loc_1800072F5
0x1800072e0  mov     [rax], r8w
0x1800072e4  add     rdi, 2
0x1800072e8  add     rax, 2
0x1800072ec  dec     rcx
0x1800072ef  sub     rdx, 1
0x1800072f3  jnz     short loc_1800072D1
0x1800072f5  test    rdx, rdx
0x1800072f8  lea     rcx, [rax-2]
0x1800072fc  cmovnz  rcx, rax
0x180007300  mov     [rcx], r15w
0x180007304  mov     [rsp+2C8h+var_294], r15d
0x180007309  jmp     loc_180007260
0x18000730e  mov     esi, 57h ; 'W'
0x180007313  jmp     loc_18000727A
```
