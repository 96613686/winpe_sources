# UbpmUtilsQueryToken(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x180025430`
- end: `0x1800255d7`
- name: `?UbpmUtilsQueryToken@@YAKPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `423`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022054`

## callees

- `0x180025430`
- `0x180032e38`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002545f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800254b9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002545f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800254b9`
- `ntdll!RtlFreeHeap` at `0x1800255ca`
- `ntdll!RtlFreeHeap` at `0x1800255ca`
- `ntdll!RtlAllocateHeap` at `0x180025490`
- `ntdll!RtlAllocateHeap` at `0x180025490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002557f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002557f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025531`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025531`

## pseudocode

```c
DWORD __fastcall UbpmUtilsQueryToken(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, void **a3)
{
  PVOID Heap; // rbx
  DWORD result; // eax
  unsigned int v8; // ebx
  DWORD LastError; // eax
  DWORD v10; // edi
  DWORD TokenInformationLength; // [rsp+58h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenInformationClass, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TokenInformationLength);
    if ( Heap )
    {
      if ( GetTokenInformation(
             TokenHandle,
             TokenInformationClass,
             Heap,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        result = 0;
        *a3 = Heap;
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        return v10;
      }
    }
    else
    {
      SetLastError(8u);
      result = GetLastError();
      v8 = result;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, result);
        return v8;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, 13);
    return 13;
  }
  return result;
}

```

## disassembly

```asm
0x180025430  mov     [rsp+arg_8], rbp
0x180025435  mov     [rsp+arg_10], rsi
0x18002543a  push    rdi
0x18002543b  sub     rsp, 30h
0x18002543f  mov     rdi, r8
0x180025442  mov     [rsp+38h+TokenInformationLength], 0
0x18002544a  lea     rax, [rsp+38h+TokenInformationLength]
0x18002544f  xor     r8d, r8d; TokenInformation
0x180025452  xor     r9d, r9d; TokenInformationLength
0x180025455  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002545a  mov     esi, edx
0x18002545c  mov     rbp, rcx
0x18002545f  call    cs:__imp_GetTokenInformation
0x180025465  test    eax, eax
0x180025467  jnz     short loc_180025474
0x180025469  call    cs:__imp_GetLastError
0x18002546f  cmp     eax, 7Ah ; 'z'
0x180025472  jnz     short loc_1800254E1
0x180025474  mov     rcx, gs:60h
0x18002547d  mov     edx, 8; Flags
0x180025482  mov     r8d, [rsp+38h+TokenInformationLength]; Size
0x180025487  mov     [rsp+38h+arg_0], rbx
0x18002548c  mov     rcx, [rcx+30h]; HeapHandle
0x180025490  call    cs:__imp_RtlAllocateHeap
0x180025496  mov     rbx, rax
0x180025499  test    rax, rax
0x18002549c  jz      loc_18002552C
0x1800254a2  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800254a7  lea     rax, [rsp+38h+TokenInformationLength]
0x1800254ac  mov     r8, rbx; TokenInformation
0x1800254af  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800254b4  mov     edx, esi; TokenInformationClass
0x1800254b6  mov     rcx, rbp; TokenHandle
0x1800254b9  call    cs:__imp_GetTokenInformation
0x1800254bf  test    eax, eax
0x1800254c1  jz      loc_18002557F
0x1800254c7  xor     eax, eax
0x1800254c9  mov     [rdi], rbx
0x1800254cc  mov     rbx, [rsp+38h+arg_0]
0x1800254d1  mov     rbp, [rsp+38h+arg_8]
0x1800254d6  mov     rsi, [rsp+38h+arg_10]
0x1800254db  add     rsp, 30h
0x1800254df  pop     rdi
0x1800254e0  retn
0x1800254e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254e8  lea     rdx, WPP_GLOBAL_Control
0x1800254ef  cmp     rcx, rdx
0x1800254f2  jnz     short loc_180025509
0x1800254f4  mov     rbp, [rsp+38h+arg_8]
0x1800254f9  mov     eax, 0Dh
0x1800254fe  mov     rsi, [rsp+38h+arg_10]
0x180025503  add     rsp, 30h
0x180025507  pop     rdi
0x180025508  retn
0x180025509  test    byte ptr [rcx+1Ch], 1
0x18002550d  jz      short loc_1800254F4
0x18002550f  mov     rcx, [rcx+10h]
0x180025513  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18002551a  mov     edx, 1Dh
0x18002551f  mov     r9d, 0Dh
0x180025525  call    WPP_SF_d
0x18002552a  jmp     short loc_1800254F4
0x18002552c  mov     ecx, 8; dwErrCode
0x180025531  call    cs:__imp_SetLastError
0x180025537  call    cs:__imp_GetLastError
0x18002553d  mov     ebx, eax
0x18002553f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025546  lea     rdx, WPP_GLOBAL_Control
0x18002554d  cmp     rcx, rdx
0x180025550  jz      loc_1800254CC
0x180025556  test    byte ptr [rcx+1Ch], 1
0x18002555a  jz      loc_1800254CC
0x180025560  mov     rcx, [rcx+10h]
0x180025564  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18002556b  mov     edx, 1Eh
0x180025570  mov     r9d, eax
0x180025573  call    WPP_SF_d
0x180025578  mov     eax, ebx
0x18002557a  jmp     loc_1800254CC
0x18002557f  call    cs:__imp_GetLastError
0x180025585  mov     edi, eax
0x180025587  mov     rcx, cs:WPP_GLOBAL_Control
0x18002558e  lea     rdx, WPP_GLOBAL_Control
0x180025595  cmp     rcx, rdx
0x180025598  jz      short loc_1800255B8
0x18002559a  test    byte ptr [rcx+1Ch], 1
0x18002559e  jz      short loc_1800255B8
0x1800255a0  mov     rcx, [rcx+10h]
0x1800255a4  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x1800255ab  mov     edx, 1Fh
0x1800255b0  mov     r9d, eax
0x1800255b3  call    WPP_SF_d
0x1800255b8  mov     rcx, gs:60h
0x1800255c1  mov     r8, rbx; P
0x1800255c4  xor     edx, edx; Flags
0x1800255c6  mov     rcx, [rcx+30h]; HeapHandle
0x1800255ca  call    cs:__imp_RtlFreeHeap
0x1800255d0  mov     eax, edi
0x1800255d2  jmp     loc_1800254CC
```
