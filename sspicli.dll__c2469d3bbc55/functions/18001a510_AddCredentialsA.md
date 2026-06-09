# AddCredentialsA

- ea: `0x18001a510`
- end: `0x18001a655`
- name: `AddCredentialsA`
- size: `325`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle hCredentials, LPSTR pszPrincipal, LPSTR pszPackage, unsigned int fCredentialUse, void *pAuthData, SEC_GET_KEY_FN pGetKeyFn, void *pvGetKeyArgument, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007b58`
- `0x18001a510`
- `0x18001b088`
- `0x18001b38c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a5b7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a5b7`

## pseudocode

```c
SECURITY_STATUS __stdcall AddCredentialsA(
        PCredHandle hCredentials,
        LPSTR pszPrincipal,
        LPSTR pszPackage,
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
  result = SecLocatePackageExA(0, pszPackage, (struct _DLL_SECURITY_PACKAGE **)&lpTlsValue);
  if ( result >= 0 )
  {
    v14 = lpTlsValue;
    if ( *(_QWORD *)(*((_QWORD *)lpTlsValue + 20) + 176LL) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v13, *((_QWORD *)lpTlsValue + 13), fCredentialUse);
      TlsSetValue(SecTlsPackage, v14);
      v15 = (*(__int64 (__fastcall **)(PCredHandle, LPSTR, LPSTR, _QWORD, void *, SEC_GET_KEY_FN, void *, PTimeStamp))(v14[20] + 176LL))(
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
          20,
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
0x18001a510  mov     rax, rsp
0x18001a513  push    rbx
0x18001a514  push    rbp
0x18001a515  push    rsi
0x18001a516  push    rdi
0x18001a517  push    r14
0x18001a519  push    r15
0x18001a51b  sub     rsp, 58h
0x18001a51f  mov     qword ptr [rax+18h], 0
0x18001a527  mov     ebp, r9d
0x18001a52a  mov     rsi, r8
0x18001a52d  mov     r14, rdx
0x18001a530  mov     rdi, rcx
0x18001a533  test    r8, r8
0x18001a536  jnz     short loc_18001A542
0x18001a538  mov     eax, 80090305h
0x18001a53d  jmp     loc_18001A648
0x18001a542  lea     r8, [rsp+88h+lpTlsValue]
0x18001a54a  mov     rdx, rsi
0x18001a54d  xor     ecx, ecx; int
0x18001a54f  call    SecLocatePackageExA
0x18001a554  test    eax, eax
0x18001a556  js      loc_18001A648
0x18001a55c  mov     rbx, [rsp+88h+lpTlsValue]
0x18001a564  mov     rax, [rbx+0A0h]
0x18001a56b  cmp     qword ptr [rax+0B0h], 0
0x18001a573  jnz     short loc_18001A57F
0x18001a575  mov     eax, 80090302h
0x18001a57a  jmp     loc_18001A648
0x18001a57f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a586  lea     r15, WPP_GLOBAL_Control
0x18001a58d  cmp     rcx, r15
0x18001a590  jz      short loc_18001A5AE
0x18001a592  test    byte ptr [rcx+1Ch], 4
0x18001a596  jz      short loc_18001A5AE
0x18001a598  mov     r9, [rbx+68h]
0x18001a59c  mov     edx, 13h
0x18001a5a1  mov     rcx, [rcx+10h]
0x18001a5a5  mov     dword ptr [rsp+88h+var_68], ebp
0x18001a5a9  call    WPP_SF_Sd
0x18001a5ae  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001a5b4  mov     rdx, rbx; lpTlsValue
0x18001a5b7  call    cs:__imp_TlsSetValue
0x18001a5bd  mov     rcx, [rsp+88h+ptsExpiry]
0x18001a5c5  mov     r9d, ebp
0x18001a5c8  mov     rax, [rbx+0A0h]
0x18001a5cf  mov     r8, rsi
0x18001a5d2  mov     [rsp+88h+var_50], rcx
0x18001a5d7  mov     rdx, r14
0x18001a5da  mov     rcx, [rsp+88h+pvGetKeyArgument]
0x18001a5e2  mov     [rsp+88h+var_58], rcx
0x18001a5e7  mov     rcx, [rsp+88h+pGetKeyFn]
0x18001a5ef  mov     rax, [rax+0B0h]
0x18001a5f6  mov     [rsp+88h+var_60], rcx
0x18001a5fb  mov     rcx, [rsp+88h+pAuthData]
0x18001a603  mov     [rsp+88h+var_68], rcx
0x18001a608  mov     rcx, rdi
0x18001a60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a610  mov     ebx, eax
0x18001a612  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a619  cmp     rcx, r15
0x18001a61c  jz      short loc_18001A646
0x18001a61e  test    byte ptr [rcx+1Ch], 4
0x18001a622  jz      short loc_18001A646
0x18001a624  mov     r8, [rdi]
0x18001a627  mov     edx, 14h
0x18001a62c  mov     rcx, [rcx+10h]
0x18001a630  mov     r9d, eax
0x18001a633  mov     [rsp+88h+var_60], r8
0x18001a638  mov     r8, [rdi+8]
0x18001a63c  mov     [rsp+88h+var_68], r8
0x18001a641  call    WPP_SF_DPP
0x18001a646  mov     eax, ebx
0x18001a648  add     rsp, 58h
0x18001a64c  pop     r15
0x18001a64e  pop     r14
0x18001a650  pop     rdi
0x18001a651  pop     rsi
0x18001a652  pop     rbp
0x18001a653  pop     rbx
0x18001a654  retn
```
