# pCopySubscription

- ea: `0x18000665c`
- end: `0x18000672b`
- name: `pCopySubscription`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180006a84`

## callees

- `0x180002218`
- `0x180002250`
- `0x18000665c`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006678`

## string_xrefs

- `0x1800066bb`: `pCopySubscription`
- `0x180006689`: `Failed to allocate memory for copy of subscription (SEQ8)`

## pseudocode

```c
__int64 __fastcall pCopySubscription(__int64 a1)
{
  __int64 result; // rax
  DWORD LastError; // ebx
  int *v4; // rax
  __int64 v5; // rcx
  LPCWSTR lpModuleName; // [rsp+68h] [rbp+0h]

  result = ConstructListItem(64);
  if ( result )
  {
    *(_OWORD *)result = *(_OWORD *)a1;
    *(_OWORD *)(result + 16) = *(_OWORD *)(a1 + 16);
    *(_OWORD *)(result + 32) = *(_OWORD *)(a1 + 32);
    *(_OWORD *)(result + 48) = *(_OWORD *)(a1 + 48);
    v5 = *(_QWORD *)(a1 + 40);
    if ( v5 )
      ++*(_DWORD *)(v5 + 24);
    *(_QWORD *)(result + 40) = v5;
  }
  else
  {
    LastError = GetLastError();
    v4 = (int *)ConstructPartialMsgW(0x2000096u, "Failed to allocate memory for copy of subscription (SEQ8)");
    WdsSetupLogMessageW(
      v4,
      589824,
      (__int64)L"D",
      0,
      0xC0Eu,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      L"pCopySubscription",
      lpModuleName,
      LastError,
      0,
      0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000665c  mov     [rsp+arg_0], rbx
0x180006661  push    rdi
0x180006662  sub     rsp, 60h
0x180006666  mov     rbx, rcx
0x180006669  mov     ecx, 40h ; '@'
0x18000666e  call    ConstructListItem
0x180006673  test    rax, rax
0x180006676  jnz     short loc_1800066F1
0x180006678  call    cs:__imp_GetLastError
0x18000667f  nop     dword ptr [rax+rax+00h]
0x180006684  mov     rdi, [rsp+68h]
0x180006689  lea     rdx, aFailedToAlloca; "Failed to allocate memory for copy of s"...
0x180006690  mov     ecx, 2000096h; unsigned int
0x180006695  mov     ebx, eax
0x180006697  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000669c  mov     [rsp+68h+var_18], 0; int
0x1800066a4  lea     r8, aD_1; "D"
0x1800066ab  mov     [rsp+68h+var_20], 0; __int64
0x1800066b4  mov     rcx, rax; int
0x1800066b7  mov     [rsp+68h+var_28], ebx; int
0x1800066bb  lea     rax, aPcopysubscript; "pCopySubscription"
0x1800066c2  mov     [rsp+68h+lpModuleName], rdi; lpModuleName
0x1800066c7  xor     r9d, r9d; int
0x1800066ca  mov     [rsp+68h+var_38], rax; __int64
0x1800066cf  mov     edx, 90000h; int
0x1800066d4  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x1800066db  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x1800066e0  mov     [rsp+68h+var_48], 0C0Eh; int
0x1800066e8  call    WdsSetupLogMessageW
0x1800066ed  xor     eax, eax
0x1800066ef  jmp     short loc_18000671F
0x1800066f1  movups  xmm0, xmmword ptr [rbx]
0x1800066f4  movups  xmmword ptr [rax], xmm0
0x1800066f7  movups  xmm1, xmmword ptr [rbx+10h]
0x1800066fb  movups  xmmword ptr [rax+10h], xmm1
0x1800066ff  movups  xmm0, xmmword ptr [rbx+20h]
0x180006703  movups  xmmword ptr [rax+20h], xmm0
0x180006707  movups  xmm1, xmmword ptr [rbx+30h]
0x18000670b  movups  xmmword ptr [rax+30h], xmm1
0x18000670f  mov     rcx, [rbx+28h]
0x180006713  test    rcx, rcx
0x180006716  jz      short loc_18000671B
0x180006718  inc     dword ptr [rcx+18h]
0x18000671b  mov     [rax+28h], rcx
0x18000671f  mov     rbx, [rsp+68h+arg_0]
0x180006724  add     rsp, 60h
0x180006728  pop     rdi
0x180006729  retn
```
