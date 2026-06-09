# ScGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x140030a5c`
- end: `0x140030bdb`
- name: `?ScGetTokenInformation@@YAKPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `383`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, void **)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140029908`
- `0x1400322dc`
- `0x140035aa0`
- `0x14003ae4c`
- `0x140062d1c`
- `0x140083168`

## callees

- `0x140004c58`
- `0x140030a5c`
- `0x1400824c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030b2b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140030a85`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140030b21`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140030a85`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140030b21`
- `ntdll!RtlFreeHeap` at `0x140030b83`
- `ntdll!RtlFreeHeap` at `0x140030b83`
- `ntdll!RtlAllocateHeap` at `0x140030abd`
- `ntdll!RtlAllocateHeap` at `0x140030abd`

## pseudocode

```c
__int64 __fastcall ScGetTokenInformation(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, void **a3)
{
  DWORD LastError; // eax
  PVOID Heap; // rbx
  DWORD v9; // esi
  __int64 v10; // r8
  SIZE_T Size; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(Size) = 0;
  GetTokenInformation(TokenHandle, TokenInformationClass, 0, 0, (PDWORD)&Size);
  LastError = GetLastError();
  if ( LastError == 122 && (_DWORD)Size )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    if ( Heap )
    {
      if ( GetTokenInformation(TokenHandle, TokenInformationClass, Heap, Size, (PDWORD)&Size) )
      {
        *a3 = Heap;
        return 0;
      }
      else
      {
        v9 = GetLastError();
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_ddqd(WPP_GLOBAL_Control->StubInfo, 46, v10, (unsigned int)TokenInformationClass, Size, TokenHandle, v9);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        return v9;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->StubInfo,
          45,
          WPP_8f086be6c6f937952c5e847c48275da5_Traceguids,
          (unsigned int)TokenInformationClass);
      return 8;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_ddqd(
        WPP_GLOBAL_Control->StubInfo,
        44,
        (unsigned int)Size,
        (unsigned int)TokenInformationClass,
        Size,
        TokenHandle,
        LastError);
    return 13;
  }
}

```

## disassembly

```asm
0x140030a5c  mov     rax, rsp
0x140030a5f  push    rbx
0x140030a60  push    rbp
0x140030a61  push    rsi
0x140030a62  push    rdi
0x140030a63  sub     rsp, 48h
0x140030a67  mov     dword ptr [rax+20h], 0
0x140030a6e  lea     rax, [rax+20h]
0x140030a72  mov     rsi, r8
0x140030a75  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x140030a7a  xor     r9d, r9d; TokenInformationLength
0x140030a7d  xor     r8d, r8d; TokenInformation
0x140030a80  mov     edi, edx
0x140030a82  mov     rbp, rcx
0x140030a85  call    cs:__imp_GetTokenInformation
0x140030a8b  call    cs:__imp_GetLastError
0x140030a91  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x140030a99  mov     r9d, eax
0x140030a9c  cmp     eax, 7Ah ; 'z'
0x140030a9f  jnz     loc_140030B94
0x140030aa5  test    r8d, r8d
0x140030aa8  jz      loc_140030B94
0x140030aae  mov     rcx, gs:60h
0x140030ab7  xor     edx, edx; Flags
0x140030ab9  mov     rcx, [rcx+30h]; HeapHandle
0x140030abd  call    cs:__imp_RtlAllocateHeap
0x140030ac3  mov     rbx, rax
0x140030ac6  test    rax, rax
0x140030ac9  jnz     short loc_140030B04
0x140030acb  mov     rcx, cs:WPP_GLOBAL_Control
0x140030ad2  lea     rax, WPP_GLOBAL_Control
0x140030ad9  cmp     rcx, rax
0x140030adc  jz      short loc_140030AFA
0x140030ade  test    byte ptr [rcx+1Ch], 1
0x140030ae2  jz      short loc_140030AFA
0x140030ae4  mov     rcx, [rcx+10h]
0x140030ae8  lea     edx, [rbx+2Dh]
0x140030aeb  mov     r9d, edi
0x140030aee  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140030af5  call    WPP_SF_d
0x140030afa  mov     eax, 8
0x140030aff  jmp     loc_140030BD2
0x140030b04  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x140030b0c  lea     rax, [rsp+68h+Size]
0x140030b14  mov     r8, rbx; TokenInformation
0x140030b17  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x140030b1c  mov     edx, edi; TokenInformationClass
0x140030b1e  mov     rcx, rbp; TokenHandle
0x140030b21  call    cs:__imp_GetTokenInformation
0x140030b27  test    eax, eax
0x140030b29  jnz     short loc_140030B8D
0x140030b2b  call    cs:__imp_GetLastError
0x140030b31  mov     esi, eax
0x140030b33  mov     rcx, cs:WPP_GLOBAL_Control
0x140030b3a  lea     rax, WPP_GLOBAL_Control
0x140030b41  cmp     rcx, rax
0x140030b44  jz      short loc_140030B71
0x140030b46  test    byte ptr [rcx+1Ch], 1
0x140030b4a  jz      short loc_140030B71
0x140030b4c  mov     eax, dword ptr [rsp+68h+Size]
0x140030b53  mov     edx, 2Eh ; '.'
0x140030b58  mov     rcx, [rcx+10h]
0x140030b5c  mov     r9d, edi
0x140030b5f  mov     [rsp+68h+var_38], esi
0x140030b63  mov     [rsp+68h+var_40], rbp
0x140030b68  mov     dword ptr [rsp+68h+ReturnLength], eax
0x140030b6c  call    WPP_SF_ddqd
0x140030b71  mov     rcx, gs:60h
0x140030b7a  mov     r8, rbx; P
0x140030b7d  xor     edx, edx; Flags
0x140030b7f  mov     rcx, [rcx+30h]; HeapHandle
0x140030b83  call    cs:__imp_RtlFreeHeap
0x140030b89  mov     eax, esi
0x140030b8b  jmp     short loc_140030BD2
0x140030b8d  mov     [rsi], rbx
0x140030b90  xor     eax, eax
0x140030b92  jmp     short loc_140030BD2
0x140030b94  mov     rcx, cs:WPP_GLOBAL_Control
0x140030b9b  lea     rax, WPP_GLOBAL_Control
0x140030ba2  cmp     rcx, rax
0x140030ba5  jz      short loc_140030BCD
0x140030ba7  test    byte ptr [rcx+1Ch], 1
0x140030bab  jz      short loc_140030BCD
0x140030bad  mov     rcx, [rcx+10h]
0x140030bb1  mov     edx, 2Ch ; ','
0x140030bb6  mov     [rsp+68h+var_38], r9d
0x140030bbb  mov     r9d, edi
0x140030bbe  mov     [rsp+68h+var_40], rbp
0x140030bc3  mov     dword ptr [rsp+68h+ReturnLength], r8d
0x140030bc8  call    WPP_SF_ddqd
0x140030bcd  mov     eax, 0Dh
0x140030bd2  add     rsp, 48h
0x140030bd6  pop     rdi
0x140030bd7  pop     rsi
0x140030bd8  pop     rbp
0x140030bd9  pop     rbx
0x140030bda  retn
```
