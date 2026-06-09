# HashCompute::init(void)

- ea: `0x180075868`
- end: `0x180075a8f`
- name: `?init@HashCompute@@QEAAKXZ`
- size: `551`
- prototype: `unsigned int __fastcall(HashCompute *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18006e8e4`

## callees

- `0x18000cc40`
- `0x180027910`
- `0x180056954`
- `0x18005dcd4`
- `0x180075868`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180075a2c`
- `ntdll!RtlNtStatusToDosError` at `0x180075a2c`
- `bcrypt!BCryptGetProperty` at `0x180075907`
- `bcrypt!BCryptGetProperty` at `0x1800759d8`
- `bcrypt!BCryptGetProperty` at `0x180075907`
- `bcrypt!BCryptGetProperty` at `0x1800759d8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007588e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007588e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180075a64`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180075a64`

## pseudocode

```c
__int64 __fastcall HashCompute::init(HashCompute *this)
{
  int Property; // ebx
  _QWORD *v2; // r10
  __int64 v3; // rdx
  ULONG v4; // ebx
  ULONG pcbResult; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]

  v7 = HIDWORD(this);
  pcbResult = 0;
  Property = BCryptOpenAlgorithmProvider(&hAlgorithm, L"SHA256", 0, 0);
  if ( Property < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    v3 = 10;
    goto LABEL_22;
  }
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", (PUCHAR)&dwBytes, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    v3 = 11;
    goto LABEL_22;
  }
  pbHashObject = (PUCHAR)operator new(dwBytes);
  if ( !pbHashObject )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2b8d55565e60367fc767d22ca087624d_Traceguids);
    }
    v4 = 14;
    goto LABEL_24;
  }
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", &dword_1800C074C, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    _InterlockedIncrement(&dword_1800C0760);
    return 0;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = 13;
LABEL_22:
    WPP_SF_d(v2[2], v3, WPP_2b8d55565e60367fc767d22ca087624d_Traceguids, (unsigned int)Property);
  }
LABEL_23:
  v4 = RtlNtStatusToDosError(Property);
LABEL_24:
  if ( pbHashObject )
  {
    operator delete(pbHashObject);
    pbHashObject = 0;
  }
  if ( hAlgorithm )
  {
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    hAlgorithm = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180075868  mov     qword ptr [rsp+arg_0], rcx
0x18007586d  push    rbx
0x18007586e  sub     rsp, 30h
0x180075872  xor     r9d, r9d; dwFlags
0x180075875  mov     [rsp+38h+arg_0], 0
0x18007587d  xor     r8d, r8d; pszImplementation
0x180075880  lea     rdx, pszAlgId; "SHA256"
0x180075887  lea     rcx, hAlgorithm; phAlgorithm
0x18007588e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180075895  nop     dword ptr [rax+rax+00h]
0x18007589a  mov     ebx, eax
0x18007589c  test    eax, eax
0x18007589e  jns     short loc_1800758DA
0x1800758a0  mov     r10, cs:WPP_GLOBAL_Control
0x1800758a7  lea     rcx, WPP_GLOBAL_Control
0x1800758ae  cmp     r10, rcx
0x1800758b1  jz      loc_180075A2A
0x1800758b7  test    dword ptr [r10+1Ch], 40000h
0x1800758bf  jz      loc_180075A2A
0x1800758c5  cmp     byte ptr [r10+19h], 2
0x1800758ca  jb      loc_180075A2A
0x1800758d0  mov     edx, 0Ah
0x1800758d5  jmp     loc_180075A17
0x1800758da  mov     rcx, cs:hAlgorithm; hObject
0x1800758e1  lea     rax, [rsp+38h+arg_0]
0x1800758e6  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800758ee  lea     r8, dwBytes; pbOutput
0x1800758f5  mov     r9d, 4; cbOutput
0x1800758fb  mov     [rsp+38h+pcbResult], rax; pcbResult
0x180075900  lea     rdx, pszProperty; "ObjectLength"
0x180075907  call    cs:__imp_BCryptGetProperty
0x18007590e  nop     dword ptr [rax+rax+00h]
0x180075913  mov     ebx, eax
0x180075915  test    eax, eax
0x180075917  jns     short loc_180075953
0x180075919  mov     r10, cs:WPP_GLOBAL_Control
0x180075920  lea     rcx, WPP_GLOBAL_Control
0x180075927  cmp     r10, rcx
0x18007592a  jz      loc_180075A2A
0x180075930  test    dword ptr [r10+1Ch], 40000h
0x180075938  jz      loc_180075A2A
0x18007593e  cmp     byte ptr [r10+19h], 2
0x180075943  jb      loc_180075A2A
0x180075949  mov     edx, 0Bh
0x18007594e  jmp     loc_180075A17
0x180075953  mov     ecx, cs:dwBytes; dwBytes
0x180075959  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007595e  mov     cs:pbHashObject, rax
0x180075965  test    rax, rax
0x180075968  jnz     short loc_1800759AB
0x18007596a  mov     rax, cs:WPP_GLOBAL_Control
0x180075971  lea     rcx, WPP_GLOBAL_Control
0x180075978  cmp     rax, rcx
0x18007597b  jz      short loc_1800759A1
0x18007597d  test    dword ptr [rax+1Ch], 40000h
0x180075984  jz      short loc_1800759A1
0x180075986  cmp     byte ptr [rax+19h], 2
0x18007598a  jb      short loc_1800759A1
0x18007598c  mov     rcx, [rax+10h]
0x180075990  lea     r8, WPP_2b8d55565e60367fc767d22ca087624d_Traceguids
0x180075997  mov     edx, 0Ch
0x18007599c  call    WPP_SF_
0x1800759a1  mov     ebx, 0Eh
0x1800759a6  jmp     loc_180075A3A
0x1800759ab  mov     rcx, cs:hAlgorithm; hObject
0x1800759b2  lea     rax, [rsp+38h+arg_0]
0x1800759b7  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800759bf  lea     r8, dword_1800C074C; pbOutput
0x1800759c6  mov     r9d, 4; cbOutput
0x1800759cc  mov     [rsp+38h+pcbResult], rax; pcbResult
0x1800759d1  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800759d8  call    cs:__imp_BCryptGetProperty
0x1800759df  nop     dword ptr [rax+rax+00h]
0x1800759e4  mov     ebx, eax
0x1800759e6  test    eax, eax
0x1800759e8  jns     loc_180075A7F
0x1800759ee  mov     r10, cs:WPP_GLOBAL_Control
0x1800759f5  lea     rcx, WPP_GLOBAL_Control
0x1800759fc  cmp     r10, rcx
0x1800759ff  jz      short loc_180075A2A
0x180075a01  test    dword ptr [r10+1Ch], 40000h
0x180075a09  jz      short loc_180075A2A
0x180075a0b  cmp     byte ptr [r10+19h], 2
0x180075a10  jb      short loc_180075A2A
0x180075a12  mov     edx, 0Dh
0x180075a17  mov     rcx, [r10+10h]
0x180075a1b  lea     r8, WPP_2b8d55565e60367fc767d22ca087624d_Traceguids
0x180075a22  mov     r9d, ebx
0x180075a25  call    WPP_SF_d
0x180075a2a  mov     ecx, ebx; Status
0x180075a2c  call    cs:__imp_RtlNtStatusToDosError
0x180075a33  nop     dword ptr [rax+rax+00h]
0x180075a38  mov     ebx, eax
0x180075a3a  mov     rcx, cs:pbHashObject; void *
0x180075a41  test    rcx, rcx
0x180075a44  jz      short loc_180075A56
0x180075a46  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180075a4b  mov     cs:pbHashObject, 0
0x180075a56  mov     rcx, cs:hAlgorithm; hAlgorithm
0x180075a5d  test    rcx, rcx
0x180075a60  jz      short loc_180075A7B
0x180075a62  xor     edx, edx; dwFlags
0x180075a64  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180075a6b  nop     dword ptr [rax+rax+00h]
0x180075a70  mov     cs:hAlgorithm, 0
0x180075a7b  mov     eax, ebx
0x180075a7d  jmp     short loc_180075A88
0x180075a7f  lock inc cs:dword_1800C0760
0x180075a86  xor     eax, eax
0x180075a88  add     rsp, 30h
0x180075a8c  pop     rbx
0x180075a8d  retn
```
