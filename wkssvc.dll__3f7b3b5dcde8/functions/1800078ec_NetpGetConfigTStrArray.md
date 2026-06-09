# NetpGetConfigTStrArray

- ea: `0x1800078ec`
- end: `0x1800079be`
- name: `NetpGetConfigTStrArray`
- size: `210`
- prototype: `__int64 __fastcall(HKEY *, __int64, BYTE **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006e04`

## callees

- `0x180007604`
- `0x180007620`
- `0x180007710`
- `0x1800078ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000797b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000797b`

## pseudocode

```c
__int64 __fastcall NetpGetConfigTStrArray(HKEY *a1, __int64 a2, BYTE **a3)
{
  __int64 result; // rax
  BYTE *lpData; // rdi
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int v11; // [rsp+4Ch] [rbp+14h]

  v11 = HIDWORD(a2);
  *a3 = 0;
  Type = 0;
  cbData = 0;
  if ( !a1 )
    return 87;
  result = NetpGetWinRegConfigMaxSizes(*a1, a2, &cbData);
  if ( !(_DWORD)result )
  {
    if ( !cbData )
      return 2147;
    lpData = (BYTE *)NetpMemoryAllocate(cbData);
    if ( !lpData )
      return 8;
    v7 = RegQueryValueExW(*a1, L"OtherDomains", 0, &Type, lpData, &cbData);
    v8 = v7;
    if ( v7 == 2 )
    {
      v8 = 2147;
LABEL_13:
      NetpMemoryFree(lpData);
      return v8;
    }
    if ( v7 )
      goto LABEL_13;
    if ( Type != 7 )
    {
      v8 = 13;
      goto LABEL_13;
    }
    *a3 = lpData;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800078ec  mov     rax, rsp
0x1800078ef  mov     [rax+18h], rbx
0x1800078f3  mov     [rax+20h], rsi
0x1800078f7  mov     [rax+10h], rdx
0x1800078fb  push    rdi
0x1800078fc  sub     rsp, 30h
0x180007900  mov     qword ptr [r8], 0
0x180007907  mov     rsi, r8
0x18000790a  mov     dword ptr [rax+8], 0
0x180007911  mov     rbx, rcx
0x180007914  mov     dword ptr [rax+10h], 0
0x18000791b  test    rcx, rcx
0x18000791e  jnz     short loc_180007928
0x180007920  lea     eax, [rcx+57h]
0x180007923  jmp     loc_1800079AE
0x180007928  mov     rcx, [rcx]
0x18000792b  lea     r8, [rsp+38h+cbData]
0x180007930  call    NetpGetWinRegConfigMaxSizes
0x180007935  test    eax, eax
0x180007937  jnz     short loc_1800079AE
0x180007939  mov     ecx, [rsp+38h+cbData]
0x18000793d  test    ecx, ecx
0x18000793f  jnz     short loc_180007948
0x180007941  mov     eax, 863h
0x180007946  jmp     short loc_1800079AE
0x180007948  call    NetpMemoryAllocate
0x18000794d  mov     rdi, rax
0x180007950  test    rax, rax
0x180007953  jnz     short loc_18000795A
0x180007955  lea     eax, [rdi+8]
0x180007958  jmp     short loc_1800079AE
0x18000795a  mov     rcx, [rbx]; hKey
0x18000795d  lea     rax, [rsp+38h+cbData]
0x180007962  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180007967  lea     r9, [rsp+38h+Type]; lpType
0x18000796c  xor     r8d, r8d; lpReserved
0x18000796f  mov     [rsp+38h+lpData], rdi; lpData
0x180007974  lea     rdx, aOtherdomains; "OtherDomains"
0x18000797b  call    cs:__imp_RegQueryValueExW
0x180007981  mov     ebx, eax
0x180007983  cmp     eax, 2
0x180007986  jnz     short loc_18000798F
0x180007988  mov     ebx, 863h
0x18000798d  jmp     short loc_18000799D
0x18000798f  test    eax, eax
0x180007991  jnz     short loc_18000799D
0x180007993  cmp     [rsp+38h+Type], 7
0x180007998  jz      short loc_1800079A9
0x18000799a  lea     ebx, [rax+0Dh]
0x18000799d  mov     rcx, rdi
0x1800079a0  call    NetpMemoryFree
0x1800079a5  mov     eax, ebx
0x1800079a7  jmp     short loc_1800079AE
0x1800079a9  mov     [rsi], rdi
0x1800079ac  xor     eax, eax
0x1800079ae  mov     rbx, [rsp+38h+arg_10]
0x1800079b3  mov     rsi, [rsp+38h+arg_18]
0x1800079b8  add     rsp, 30h
0x1800079bc  pop     rdi
0x1800079bd  retn
```
