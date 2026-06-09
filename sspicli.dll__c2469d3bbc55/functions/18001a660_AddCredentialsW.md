# AddCredentialsW

- ea: `0x18001a660`
- end: `0x18001a7a5`
- name: `AddCredentialsW`
- size: `325`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle hCredentials, LPWSTR pszPrincipal, LPWSTR pszPackage, unsigned int fCredentialUse, void *pAuthData, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180009c90`
- `0x18001a660`
- `0x18001b088`
- `0x18001b38c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a707`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a707`

## pseudocode

```c
SECURITY_STATUS __stdcall AddCredentialsW(
        PCredHandle hCredentials,
        LPWSTR pszPrincipal,
        LPWSTR pszPackage,
        unsigned int fCredentialUse,
        void *pAuthData,
        SEC_GET_KEY_FN pGetKeyFn,
        void *pvGetKeyArgument,
        PTimeStamp ptsExpiry)
{
  SECURITY_STATUS result; // eax
  int v13; // r8d
  _QWORD *v14; // rbx
  unsigned int v15; // eax
  SECURITY_STATUS v16; // ebx
  LPVOID lpTlsValue; // [rsp+A0h] [rbp+18h] BYREF

  lpTlsValue = 0;
  if ( !pszPackage )
    return -2146893051;
  result = SecLocatePackageExW(0, pszPackage, &lpTlsValue);
  if ( result >= 0 )
  {
    v14 = lpTlsValue;
    if ( *(_QWORD *)(*((_QWORD *)lpTlsValue + 21) + 176LL) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v13, *((_QWORD *)lpTlsValue + 13), fCredentialUse);
      TlsSetValue(SecTlsPackage, v14);
      v15 = (*(__int64 (__fastcall **)(PCredHandle, LPWSTR, LPWSTR, _QWORD, void *, SEC_GET_KEY_FN, void *, PTimeStamp))(v14[21] + 176LL))(
              hCredentials,
              pszPrincipal,
              pszPackage,
              fCredentialUse,
              pAuthData,
              pGetKeyFn,
              pvGetKeyArgument,
              ptsExpiry);
      v16 = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_DPP(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          hCredentials->dwUpper,
          v15,
          hCredentials->dwUpper,
          hCredentials->dwLower);
      return v16;
    }
    else
    {
      return -2146893054;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a660  mov     rax, rsp
0x18001a663  push    rbx
0x18001a664  push    rbp
0x18001a665  push    rsi
0x18001a666  push    rdi
0x18001a667  push    r14
0x18001a669  push    r15
0x18001a66b  sub     rsp, 58h
0x18001a66f  mov     qword ptr [rax+18h], 0
0x18001a677  mov     ebp, r9d
0x18001a67a  mov     rsi, r8
0x18001a67d  mov     r14, rdx
0x18001a680  mov     rdi, rcx
0x18001a683  test    r8, r8
0x18001a686  jnz     short loc_18001A692
0x18001a688  mov     eax, 80090305h
0x18001a68d  jmp     loc_18001A798
0x18001a692  lea     r8, [rsp+88h+lpTlsValue]
0x18001a69a  mov     rdx, rsi
0x18001a69d  xor     ecx, ecx
0x18001a69f  call    SecLocatePackageExW
0x18001a6a4  test    eax, eax
0x18001a6a6  js      loc_18001A798
0x18001a6ac  mov     rbx, [rsp+88h+lpTlsValue]
0x18001a6b4  mov     rax, [rbx+0A8h]
0x18001a6bb  cmp     qword ptr [rax+0B0h], 0
0x18001a6c3  jnz     short loc_18001A6CF
0x18001a6c5  mov     eax, 80090302h
0x18001a6ca  jmp     loc_18001A798
0x18001a6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6d6  lea     r15, WPP_GLOBAL_Control
0x18001a6dd  cmp     rcx, r15
0x18001a6e0  jz      short loc_18001A6FE
0x18001a6e2  test    byte ptr [rcx+1Ch], 4
0x18001a6e6  jz      short loc_18001A6FE
0x18001a6e8  mov     r9, [rbx+68h]
0x18001a6ec  mov     edx, 11h
0x18001a6f1  mov     rcx, [rcx+10h]
0x18001a6f5  mov     dword ptr [rsp+88h+var_68], ebp
0x18001a6f9  call    WPP_SF_Sd
0x18001a6fe  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001a704  mov     rdx, rbx; lpTlsValue
0x18001a707  call    cs:__imp_TlsSetValue
0x18001a70d  mov     rcx, [rsp+88h+ptsExpiry]
0x18001a715  mov     r9d, ebp
0x18001a718  mov     rax, [rbx+0A8h]
0x18001a71f  mov     r8, rsi
0x18001a722  mov     [rsp+88h+var_50], rcx
0x18001a727  mov     rdx, r14
0x18001a72a  mov     rcx, [rsp+88h+pvGetKeyArgument]
0x18001a732  mov     [rsp+88h+var_58], rcx
0x18001a737  mov     rcx, [rsp+88h+pGetKeyFn]
0x18001a73f  mov     rax, [rax+0B0h]
0x18001a746  mov     [rsp+88h+var_60], rcx
0x18001a74b  mov     rcx, [rsp+88h+pAuthData]
0x18001a753  mov     [rsp+88h+var_68], rcx
0x18001a758  mov     rcx, rdi
0x18001a75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a760  mov     ebx, eax
0x18001a762  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a769  cmp     rcx, r15
0x18001a76c  jz      short loc_18001A796
0x18001a76e  test    byte ptr [rcx+1Ch], 4
0x18001a772  jz      short loc_18001A796
0x18001a774  mov     r8, [rdi]
0x18001a777  mov     edx, 12h
0x18001a77c  mov     rcx, [rcx+10h]
0x18001a780  mov     r9d, eax
0x18001a783  mov     [rsp+88h+var_60], r8
0x18001a788  mov     r8, [rdi+8]
0x18001a78c  mov     [rsp+88h+var_68], r8
0x18001a791  call    WPP_SF_DPP
0x18001a796  mov     eax, ebx
0x18001a798  add     rsp, 58h
0x18001a79c  pop     r15
0x18001a79e  pop     r14
0x18001a7a0  pop     rdi
0x18001a7a1  pop     rsi
0x18001a7a2  pop     rbp
0x18001a7a3  pop     rbx
0x18001a7a4  retn
```
