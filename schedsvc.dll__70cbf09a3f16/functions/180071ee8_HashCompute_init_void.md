# HashCompute::init(void)

- ea: `0x180071ee8`
- end: `0x1800720f0`
- name: `?init@HashCompute@@QEAAKXZ`
- size: `520`
- prototype: `unsigned int __fastcall(HashCompute *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18006b3ac`

## callees

- `0x18001a260`
- `0x180030f80`
- `0x180054084`
- `0x18005b124`
- `0x180071ee8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18007209a`
- `ntdll!RtlNtStatusToDosError` at `0x18007209a`
- `bcrypt!BCryptGetProperty` at `0x180071f81`
- `bcrypt!BCryptGetProperty` at `0x18007204c`
- `bcrypt!BCryptGetProperty` at `0x180071f81`
- `bcrypt!BCryptGetProperty` at `0x18007204c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180071f0e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180071f0e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800720cc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800720cc`

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
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", &dword_1800BC64C, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    _InterlockedIncrement(&dword_1800BC660);
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
0x180071ee8  mov     qword ptr [rsp+arg_0], rcx
0x180071eed  push    rbx
0x180071eee  sub     rsp, 30h
0x180071ef2  xor     r9d, r9d; dwFlags
0x180071ef5  mov     [rsp+38h+arg_0], 0
0x180071efd  xor     r8d, r8d; pszImplementation
0x180071f00  lea     rdx, pszAlgId; "SHA256"
0x180071f07  lea     rcx, hAlgorithm; phAlgorithm
0x180071f0e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180071f14  mov     ebx, eax
0x180071f16  test    eax, eax
0x180071f18  jns     short loc_180071F54
0x180071f1a  mov     r10, cs:WPP_GLOBAL_Control
0x180071f21  lea     rcx, WPP_GLOBAL_Control
0x180071f28  cmp     r10, rcx
0x180071f2b  jz      loc_180072098
0x180071f31  test    dword ptr [r10+1Ch], 40000h
0x180071f39  jz      loc_180072098
0x180071f3f  cmp     byte ptr [r10+19h], 2
0x180071f44  jb      loc_180072098
0x180071f4a  mov     edx, 0Ah
0x180071f4f  jmp     loc_180072085
0x180071f54  mov     rcx, cs:hAlgorithm; hObject
0x180071f5b  lea     rax, [rsp+38h+arg_0]
0x180071f60  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180071f68  lea     r8, dwBytes; pbOutput
0x180071f6f  mov     r9d, 4; cbOutput
0x180071f75  mov     [rsp+38h+pcbResult], rax; pcbResult
0x180071f7a  lea     rdx, pszProperty; "ObjectLength"
0x180071f81  call    cs:__imp_BCryptGetProperty
0x180071f87  mov     ebx, eax
0x180071f89  test    eax, eax
0x180071f8b  jns     short loc_180071FC7
0x180071f8d  mov     r10, cs:WPP_GLOBAL_Control
0x180071f94  lea     rcx, WPP_GLOBAL_Control
0x180071f9b  cmp     r10, rcx
0x180071f9e  jz      loc_180072098
0x180071fa4  test    dword ptr [r10+1Ch], 40000h
0x180071fac  jz      loc_180072098
0x180071fb2  cmp     byte ptr [r10+19h], 2
0x180071fb7  jb      loc_180072098
0x180071fbd  mov     edx, 0Bh
0x180071fc2  jmp     loc_180072085
0x180071fc7  mov     ecx, cs:dwBytes; dwBytes
0x180071fcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180071fd2  mov     cs:pbHashObject, rax
0x180071fd9  test    rax, rax
0x180071fdc  jnz     short loc_18007201F
0x180071fde  mov     rax, cs:WPP_GLOBAL_Control
0x180071fe5  lea     rcx, WPP_GLOBAL_Control
0x180071fec  cmp     rax, rcx
0x180071fef  jz      short loc_180072015
0x180071ff1  test    dword ptr [rax+1Ch], 40000h
0x180071ff8  jz      short loc_180072015
0x180071ffa  cmp     byte ptr [rax+19h], 2
0x180071ffe  jb      short loc_180072015
0x180072000  mov     rcx, [rax+10h]
0x180072004  lea     r8, WPP_2b8d55565e60367fc767d22ca087624d_Traceguids
0x18007200b  mov     edx, 0Ch
0x180072010  call    WPP_SF_
0x180072015  mov     ebx, 0Eh
0x18007201a  jmp     loc_1800720A2
0x18007201f  mov     rcx, cs:hAlgorithm; hObject
0x180072026  lea     rax, [rsp+38h+arg_0]
0x18007202b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180072033  lea     r8, dword_1800BC64C; pbOutput
0x18007203a  mov     r9d, 4; cbOutput
0x180072040  mov     [rsp+38h+pcbResult], rax; pcbResult
0x180072045  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18007204c  call    cs:__imp_BCryptGetProperty
0x180072052  mov     ebx, eax
0x180072054  test    eax, eax
0x180072056  jns     loc_1800720E1
0x18007205c  mov     r10, cs:WPP_GLOBAL_Control
0x180072063  lea     rcx, WPP_GLOBAL_Control
0x18007206a  cmp     r10, rcx
0x18007206d  jz      short loc_180072098
0x18007206f  test    dword ptr [r10+1Ch], 40000h
0x180072077  jz      short loc_180072098
0x180072079  cmp     byte ptr [r10+19h], 2
0x18007207e  jb      short loc_180072098
0x180072080  mov     edx, 0Dh
0x180072085  mov     rcx, [r10+10h]
0x180072089  lea     r8, WPP_2b8d55565e60367fc767d22ca087624d_Traceguids
0x180072090  mov     r9d, ebx
0x180072093  call    WPP_SF_d
0x180072098  mov     ecx, ebx; Status
0x18007209a  call    cs:__imp_RtlNtStatusToDosError
0x1800720a0  mov     ebx, eax
0x1800720a2  mov     rcx, cs:pbHashObject; void *
0x1800720a9  test    rcx, rcx
0x1800720ac  jz      short loc_1800720BE
0x1800720ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800720b3  mov     cs:pbHashObject, 0
0x1800720be  mov     rcx, cs:hAlgorithm; hAlgorithm
0x1800720c5  test    rcx, rcx
0x1800720c8  jz      short loc_1800720DD
0x1800720ca  xor     edx, edx; dwFlags
0x1800720cc  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800720d2  mov     cs:hAlgorithm, 0
0x1800720dd  mov     eax, ebx
0x1800720df  jmp     short loc_1800720EA
0x1800720e1  lock inc cs:dword_1800BC660
0x1800720e8  xor     eax, eax
0x1800720ea  add     rsp, 30h
0x1800720ee  pop     rbx
0x1800720ef  retn
```
