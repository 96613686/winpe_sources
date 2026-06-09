# CVaultAlgProvider::Initialize(uchar)

- ea: `0x1800387c8`
- end: `0x1800388c7`
- name: `?Initialize@CVaultAlgProvider@@QEAAKE@Z`
- size: `255`
- prototype: `unsigned int __fastcall(CVaultAlgProvider *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001a50`

## callees

- `0x1800387c8`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180038881`
- `bcrypt!BCryptGetProperty` at `0x1800388ad`
- `bcrypt!BCryptGetProperty` at `0x180038881`
- `bcrypt!BCryptGetProperty` at `0x1800388ad`
- `bcrypt!BCryptSetProperty` at `0x180038850`
- `bcrypt!BCryptSetProperty` at `0x180038850`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180038811`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180038811`
- `ntdll!RtlNtStatusToDosError` at `0x18003881d`
- `ntdll!RtlNtStatusToDosError` at `0x18003881d`

## pseudocode

```c
ULONG __fastcall CVaultAlgProvider::Initialize(CVaultAlgProvider *this, char a2)
{
  BCRYPT_HANDLE *v2; // rbx
  UCHAR *v3; // r14
  UCHAR *v4; // rsi
  const WCHAR *v6; // rdx
  int Property; // eax
  ULONG pcbResult; // [rsp+60h] [rbp+8h] BYREF

  v2 = (BCRYPT_HANDLE *)((char *)this + 16);
  *((_DWORD *)this + 6) = 1;
  v3 = (UCHAR *)this + 32;
  pcbResult = 0;
  v4 = (UCHAR *)this + 28;
  *((_QWORD *)this + 2) = -1;
  *((_DWORD *)this + 8) = 0;
  v6 = (const WCHAR *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 7) = 0;
  Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 2, v6, 0, 0);
  if ( Property >= 0
    && (a2
     || (Property = BCryptSetProperty(*v2, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0), Property >= 0)
     && (Property = BCryptGetProperty(*v2, L"BlockLength", v4, 4u, &pcbResult, 0), Property >= 0)
     && (Property = BCryptGetProperty(*v2, L"ObjectLength", v3, 4u, &pcbResult, 0), Property >= 0)) )
  {
    return 0;
  }
  else
  {
    return RtlNtStatusToDosError(Property);
  }
}

```

## disassembly

```asm
0x1800387c8  push    rbx
0x1800387ca  push    rsi
0x1800387cb  push    rdi
0x1800387cc  push    r14
0x1800387ce  sub     rsp, 38h
0x1800387d2  lea     rbx, [rcx+10h]
0x1800387d6  mov     dword ptr [rcx+18h], 1
0x1800387dd  lea     r14, [rcx+20h]
0x1800387e1  mov     [rsp+58h+pcbResult], 0
0x1800387e9  lea     rsi, [rcx+1Ch]
0x1800387ed  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800387f4  mov     dil, dl
0x1800387f7  mov     dword ptr [r14], 0
0x1800387fe  mov     rdx, [rcx+8]; pszAlgId
0x180038802  xor     r9d, r9d; dwFlags
0x180038805  mov     rcx, rbx; phAlgorithm
0x180038808  mov     dword ptr [rsi], 0
0x18003880e  xor     r8d, r8d; pszImplementation
0x180038811  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180038817  test    eax, eax
0x180038819  jns     short loc_180038828
0x18003881b  mov     ecx, eax; Status
0x18003881d  call    cs:__imp_RtlNtStatusToDosError
0x180038823  jmp     loc_1800388BD
0x180038828  test    dil, dil
0x18003882b  jnz     loc_1800388BB
0x180038831  mov     rcx, [rbx]; hObject
0x180038834  lea     r8, pbInput; "ChainingModeCBC"
0x18003883b  mov     r9d, 20h ; ' '; cbInput
0x180038841  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180038849  lea     rdx, pszProperty; "ChainingMode"
0x180038850  call    cs:__imp_BCryptSetProperty
0x180038856  test    eax, eax
0x180038858  js      short loc_18003881B
0x18003885a  mov     rcx, [rbx]; hObject
0x18003885d  lea     rax, [rsp+58h+pcbResult]
0x180038862  mov     edi, 4
0x180038867  mov     [rsp+58h+var_30], 0; dwFlags
0x18003886f  mov     r9d, edi; cbOutput
0x180038872  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x180038877  mov     r8, rsi; pbOutput
0x18003887a  lea     rdx, aBlocklength; "BlockLength"
0x180038881  call    cs:__imp_BCryptGetProperty
0x180038887  test    eax, eax
0x180038889  js      short loc_18003881B
0x18003888b  mov     rcx, [rbx]; hObject
0x18003888e  lea     rax, [rsp+58h+pcbResult]
0x180038893  mov     [rsp+58h+var_30], 0; dwFlags
0x18003889b  lea     rdx, aObjectlength; "ObjectLength"
0x1800388a2  mov     r9d, edi; cbOutput
0x1800388a5  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x1800388aa  mov     r8, r14; pbOutput
0x1800388ad  call    cs:__imp_BCryptGetProperty
0x1800388b3  test    eax, eax
0x1800388b5  js      loc_18003881B
0x1800388bb  xor     eax, eax
0x1800388bd  add     rsp, 38h
0x1800388c1  pop     r14
0x1800388c3  pop     rdi
0x1800388c4  pop     rsi
0x1800388c5  pop     rbx
0x1800388c6  retn
```
