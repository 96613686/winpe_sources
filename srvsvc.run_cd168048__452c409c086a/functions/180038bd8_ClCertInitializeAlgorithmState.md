# ClCertInitializeAlgorithmState

- ea: `0x180038bd8`
- end: `0x180038cc9`
- name: `ClCertInitializeAlgorithmState`
- size: `241`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, BCRYPT_ALG_HANDLE *phAlgorithm)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180038b38`
- `0x180038cd0`

## callees

- `0x1800215e8`
- `0x180038bd8`
- `0x180039950`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180038caa`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180038caa`
- `bcrypt!BCryptCreateHash` at `0x180038c60`
- `bcrypt!BCryptCreateHash` at `0x180038c60`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180038bf8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180038bf8`

## pseudocode

```c
__int64 __fastcall ClCertInitializeAlgorithmState(LPCWSTR pszAlgId, BCRYPT_ALG_HANDLE *phAlgorithm)
{
  int v3; // ebp
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  NTSTATUS v6; // ecx
  ULONG v7; // ebx
  NTSTATUS Hash; // eax
  NTSTATUS v9; // edi

  v3 = (int)pszAlgId;
  v4 = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, 0, 0x20u);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = 0;
    Hash = BCryptCreateHash(*phAlgorithm, phAlgorithm + 1, 0, 0, 0, 0, 0x20u);
    v9 = Hash;
    if ( Hash >= 0 )
      return v7;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids,
        v3,
        Hash);
    }
    v6 = v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids,
        v3,
        v4);
    }
    v6 = v5;
  }
  v7 = RtlNtStatusToDosErrorNoTeb(v6);
  if ( v7 )
    ClCertUninitializeAlgorithmState(phAlgorithm);
  return v7;
}

```

## disassembly

```asm
0x180038bd8  push    rbx
0x180038bda  push    rbp
0x180038bdb  push    rsi
0x180038bdc  push    rdi
0x180038bdd  sub     rsp, 48h
0x180038be1  mov     rsi, rdx
0x180038be4  mov     rbp, rcx
0x180038be7  mov     rdx, rcx; pszAlgId
0x180038bea  mov     edi, 20h ; ' '
0x180038bef  mov     r9d, edi; dwFlags
0x180038bf2  mov     rcx, rsi; phAlgorithm
0x180038bf5  xor     r8d, r8d; pszImplementation
0x180038bf8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180038bfe  mov     ebx, eax
0x180038c00  test    eax, eax
0x180038c02  jns     short loc_180038C44
0x180038c04  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c0b  lea     rdx, WPP_GLOBAL_Control
0x180038c12  cmp     rcx, rdx
0x180038c15  jz      short loc_180038C40
0x180038c17  test    dword ptr [rcx+1Ch], 800h
0x180038c1e  jz      short loc_180038C40
0x180038c20  cmp     byte ptr [rcx+19h], 1
0x180038c24  jb      short loc_180038C40
0x180038c26  mov     rcx, [rcx+10h]
0x180038c2a  lea     edx, [rdi-7]
0x180038c2d  mov     r9, rbp
0x180038c30  mov     dword ptr [rsp+68h+pbSecret], eax
0x180038c34  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180038c3b  call    WPP_SF_Sd
0x180038c40  mov     ecx, ebx
0x180038c42  jmp     short loc_180038CAA
0x180038c44  mov     rcx, [rsi]; hAlgorithm
0x180038c47  lea     rdx, [rsi+8]; phHash
0x180038c4b  xor     ebx, ebx
0x180038c4d  mov     [rsp+68h+dwFlags], edi; dwFlags
0x180038c51  mov     [rsp+68h+cbSecret], ebx; cbSecret
0x180038c55  xor     r9d, r9d; cbHashObject
0x180038c58  xor     r8d, r8d; pbHashObject
0x180038c5b  mov     [rsp+68h+pbSecret], rbx; pbSecret
0x180038c60  call    cs:__imp_BCryptCreateHash
0x180038c66  mov     edi, eax
0x180038c68  test    eax, eax
0x180038c6a  jns     short loc_180038CBE
0x180038c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c73  lea     rdx, WPP_GLOBAL_Control
0x180038c7a  cmp     rcx, rdx
0x180038c7d  jz      short loc_180038CA8
0x180038c7f  test    dword ptr [rcx+1Ch], 800h
0x180038c86  jz      short loc_180038CA8
0x180038c88  cmp     byte ptr [rcx+19h], 1
0x180038c8c  jb      short loc_180038CA8
0x180038c8e  mov     rcx, [rcx+10h]
0x180038c92  lea     edx, [rbx+1Ah]
0x180038c95  mov     r9, rbp
0x180038c98  mov     dword ptr [rsp+68h+pbSecret], eax
0x180038c9c  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180038ca3  call    WPP_SF_Sd
0x180038ca8  mov     ecx, edi; Status
0x180038caa  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180038cb0  mov     ebx, eax
0x180038cb2  test    eax, eax
0x180038cb4  jz      short loc_180038CBE
0x180038cb6  mov     rcx, rsi
0x180038cb9  call    ClCertUninitializeAlgorithmState
0x180038cbe  mov     eax, ebx
0x180038cc0  add     rsp, 48h
0x180038cc4  pop     rdi
0x180038cc5  pop     rsi
0x180038cc6  pop     rbp
0x180038cc7  pop     rbx
0x180038cc8  retn
```
