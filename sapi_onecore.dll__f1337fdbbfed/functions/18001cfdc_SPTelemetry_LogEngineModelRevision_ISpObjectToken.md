# SPTelemetry::LogEngineModelRevision(ISpObjectToken *)

- ea: `0x18001cfdc`
- end: `0x18001d206`
- name: `?LogEngineModelRevision@SPTelemetry@@SAXPEAUISpObjectToken@@@Z`
- size: `554`
- prototype: `void __fastcall(struct ISpObjectToken *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054960`
- `0x1801ac478`
- `0x1801bb140`

## callees

- `0x18000cdb0`
- `0x180019a50`
- `0x18001cfdc`
- `0x180132008`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001d0fe`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001d154`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001d1c0`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001d0fe`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001d154`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001d1c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d0f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d146`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d1b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d0f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d146`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d1b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d133`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d133`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall SPTelemetry::LogEngineModelRevision(struct ISpObjectToken *a1)
{
  __int64 v2; // rbx
  LPCVOID v3; // rdi
  HANDLE ProcessHeap; // rax
  SIZE_T v5; // rax
  SIZE_T v6; // rax
  __int64 v7; // rcx
  _WORD *v8; // rdi
  LPCVOID v9; // rdi
  HANDLE v10; // rax
  SIZE_T v11; // rax
  SIZE_T v12; // rax
  __int64 v13; // rcx
  _WORD *v14; // rdi
  LPCVOID v15; // rdi
  HANDLE v16; // rax
  SIZE_T v17; // rax
  unsigned __int64 v18; // rax
  _WORD *v19; // rdi
  __int64 i; // rcx
  __int64 v21; // [rsp+20h] [rbp-20h] BYREF
  __int64 v22; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+30h] [rbp-10h] BYREF
  LPCVOID lpMem; // [rsp+70h] [rbp+30h] BYREF
  LPCVOID v25; // [rsp+78h] [rbp+38h] BYREF
  LPCVOID v26; // [rsp+80h] [rbp+40h] BYREF
  __int64 v27; // [rsp+88h] [rbp+48h] BYREF

  v26 = 0;
  v2 = 8;
  if ( ((int (__fastcall *)(struct ISpObjectToken *, _QWORD, LPCVOID *))a1->lpVtbl->GetStringValue)(a1, 0, &v26) < 0 )
    goto LABEL_28;
  v27 = 0;
  v25 = 0;
  lpMem = 0;
  if ( ((int (__fastcall *)(struct ISpObjectToken *, const WCHAR *, __int64 *))a1->lpVtbl->OpenKey)(
         a1,
         L"Attributes",
         &v27) >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, LPCVOID *))(*(_QWORD *)v27 + 48LL))(v27, L"Revision", &v25) < 0 )
      CSpDynamicString::operator=(&v25, L"default");
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, LPCVOID *))(*(_QWORD *)v27 + 48LL))(
           v27,
           L"DeploymentMethod",
           &lpMem) < 0 )
      CSpDynamicString::operator=(&lpMem, L"default");
    v21 = 0;
    CSpDynamicString::operator=(&v21, &lpMem);
    v22 = 0;
    CSpDynamicString::operator=(&v22, &v25);
    v23[0] = 0;
    CSpDynamicString::operator=(v23, &v26);
    SPTelemetry::LogEngineModelRevision(v23, &v22, &v21);
  }
  v3 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    v5 = HeapSize(ProcessHeap, 0, v3);
    if ( v5 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v6 = v5 >> 1;
      v7 = v6 - 1;
      if ( v6 - 1 >= 8 )
      {
        v7 = 8;
        goto LABEL_13;
      }
      if ( v6 != 1 )
      {
LABEL_13:
        v8 = lpMem;
        while ( v7 )
        {
          *v8++ = -8531;
          --v7;
        }
      }
    }
    CoTaskMemFree((LPVOID)lpMem);
    lpMem = 0;
  }
  v9 = v25;
  if ( !v25 )
    goto LABEL_26;
  v10 = GetProcessHeap();
  v11 = HeapSize(v10, 0, v9);
  if ( v11 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
  {
    v12 = v11 >> 1;
    v13 = v12 - 1;
    if ( v12 - 1 >= 8 )
    {
      v13 = 8;
      goto LABEL_22;
    }
    if ( v12 != 1 )
    {
LABEL_22:
      v14 = v25;
      while ( v13 )
      {
        *v14++ = -8531;
        --v13;
      }
    }
  }
  CoTaskMemFree((LPVOID)v25);
  v25 = 0;
LABEL_26:
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
LABEL_28:
  v15 = v26;
  if ( v26 )
  {
    v16 = GetProcessHeap();
    v17 = HeapSize(v16, 0, v15);
    if ( v17 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v18 = (v17 >> 1) - 1;
      if ( v18 >= 8 || (v2 = v18) != 0 )
      {
        v19 = v26;
        for ( i = v2; i; --i )
          *v19++ = -8531;
      }
    }
    CoTaskMemFree((LPVOID)v26);
  }
}

```

## disassembly

```asm
0x18001cfdc  push    rbp
0x18001cfde  push    rbx
0x18001cfdf  push    rsi
0x18001cfe0  push    rdi
0x18001cfe1  push    r14
0x18001cfe3  mov     rbp, rsp
0x18001cfe6  sub     rsp, 40h
0x18001cfea  mov     rdi, rcx
0x18001cfed  xor     esi, esi
0x18001cfef  mov     [rbp+arg_10], rsi
0x18001cff3  mov     rax, [rcx]
0x18001cff6  lea     r8, [rbp+arg_10]
0x18001cffa  xor     edx, edx
0x18001cffc  mov     rax, [rax+30h]
0x18001d000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d005  lea     ebx, [rsi+8]
0x18001d008  mov     r14d, 0DEADh
0x18001d00e  test    eax, eax
0x18001d010  js      loc_18001D1A9
0x18001d016  mov     [rbp+arg_18], rsi
0x18001d01a  mov     [rbp+arg_8], rsi
0x18001d01e  mov     [rbp+lpMem], rsi
0x18001d022  mov     rax, [rdi]
0x18001d025  lea     r8, [rbp+arg_18]
0x18001d029  lea     rdx, aAttributes_0; "Attributes"
0x18001d030  mov     rcx, rdi
0x18001d033  mov     rax, [rax+48h]
0x18001d037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d03c  test    eax, eax
0x18001d03e  js      loc_18001D0E7
0x18001d044  mov     rcx, [rbp+arg_18]
0x18001d048  mov     rax, [rcx]
0x18001d04b  lea     r8, [rbp+arg_8]
0x18001d04f  lea     rdx, aRevision; "Revision"
0x18001d056  mov     rax, [rax+30h]
0x18001d05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d05f  test    eax, eax
0x18001d061  jns     short loc_18001D073
0x18001d063  lea     rdx, aDefault; "default"
0x18001d06a  lea     rcx, [rbp+arg_8]
0x18001d06e  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x18001d073  mov     rcx, [rbp+arg_18]
0x18001d077  mov     rax, [rcx]
0x18001d07a  lea     r8, [rbp+lpMem]
0x18001d07e  lea     rdx, aDeploymentmeth; "DeploymentMethod"
0x18001d085  mov     rax, [rax+30h]
0x18001d089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d08e  test    eax, eax
0x18001d090  jns     short loc_18001D0A2
0x18001d092  lea     rdx, aDefault; "default"
0x18001d099  lea     rcx, [rbp+lpMem]
0x18001d09d  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x18001d0a2  mov     [rbp+var_20], rsi
0x18001d0a6  lea     rdx, [rbp+lpMem]
0x18001d0aa  lea     rcx, [rbp+var_20]
0x18001d0ae  call    ??4CSpDynamicString@@QEAAPEAGAEBV0@@Z; CSpDynamicString::operator=(CSpDynamicString const &)
0x18001d0b3  mov     [rbp+var_18], rsi
0x18001d0b7  lea     rdx, [rbp+arg_8]
0x18001d0bb  lea     rcx, [rbp+var_18]
0x18001d0bf  call    ??4CSpDynamicString@@QEAAPEAGAEBV0@@Z; CSpDynamicString::operator=(CSpDynamicString const &)
0x18001d0c4  mov     [rbp+var_10], rsi
0x18001d0c8  lea     rdx, [rbp+arg_10]
0x18001d0cc  lea     rcx, [rbp+var_10]
0x18001d0d0  call    ??4CSpDynamicString@@QEAAPEAGAEBV0@@Z; CSpDynamicString::operator=(CSpDynamicString const &)
0x18001d0d5  lea     r8, [rbp+var_20]
0x18001d0d9  lea     rdx, [rbp+var_18]
0x18001d0dd  lea     rcx, [rbp+var_10]
0x18001d0e1  call    ?LogEngineModelRevision@SPTelemetry@@SAXVCSpDynamicString@@00@Z; SPTelemetry::LogEngineModelRevision(CSpDynamicString,CSpDynamicString,CSpDynamicString)
0x18001d0e6  nop
0x18001d0e7  mov     rdi, [rbp+lpMem]
0x18001d0eb  test    rdi, rdi
0x18001d0ee  jz      short loc_18001D13D
0x18001d0f0  call    cs:__imp_GetProcessHeap
0x18001d0f6  mov     r8, rdi; lpMem
0x18001d0f9  xor     edx, edx; dwFlags
0x18001d0fb  mov     rcx, rax; hHeap
0x18001d0fe  call    cs:__imp_HeapSize
0x18001d104  lea     rcx, [rax-3]
0x18001d108  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x18001d10c  ja      short loc_18001D12F
0x18001d10e  shr     rax, 1
0x18001d111  lea     rcx, [rax-1]
0x18001d115  cmp     rcx, rbx
0x18001d118  jb      short loc_18001D11F
0x18001d11a  mov     rcx, rbx
0x18001d11d  jmp     short loc_18001D124
0x18001d11f  test    rcx, rcx
0x18001d122  jz      short loc_18001D12F
0x18001d124  movzx   eax, r14w
0x18001d128  mov     rdi, [rbp+lpMem]
0x18001d12c  rep stosw
0x18001d12f  mov     rcx, [rbp+lpMem]; pv
0x18001d133  call    cs:__imp_CoTaskMemFree
0x18001d139  mov     [rbp+lpMem], rsi
0x18001d13d  mov     rdi, [rbp+arg_8]
0x18001d141  test    rdi, rdi
0x18001d144  jz      short loc_18001D193
0x18001d146  call    cs:__imp_GetProcessHeap
0x18001d14c  mov     r8, rdi; lpMem
0x18001d14f  xor     edx, edx; dwFlags
0x18001d151  mov     rcx, rax; hHeap
0x18001d154  call    cs:__imp_HeapSize
0x18001d15a  lea     rcx, [rax-3]
0x18001d15e  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x18001d162  ja      short loc_18001D185
0x18001d164  shr     rax, 1
0x18001d167  lea     rcx, [rax-1]
0x18001d16b  cmp     rcx, rbx
0x18001d16e  jb      short loc_18001D175
0x18001d170  mov     rcx, rbx
0x18001d173  jmp     short loc_18001D17A
0x18001d175  test    rcx, rcx
0x18001d178  jz      short loc_18001D185
0x18001d17a  movzx   eax, r14w
0x18001d17e  mov     rdi, [rbp+arg_8]
0x18001d182  rep stosw
0x18001d185  mov     rcx, [rbp+arg_8]; pv
0x18001d189  call    cs:__imp_CoTaskMemFree
0x18001d18f  mov     [rbp+arg_8], rsi
0x18001d193  mov     rcx, [rbp+arg_18]
0x18001d197  test    rcx, rcx
0x18001d19a  jz      short loc_18001D1A9
0x18001d19c  mov     rax, [rcx]
0x18001d19f  mov     rax, [rax+10h]
0x18001d1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1a8  nop
0x18001d1a9  mov     rdi, [rbp+arg_10]
0x18001d1ad  test    rdi, rdi
0x18001d1b0  jz      short loc_18001D1FB
0x18001d1b2  call    cs:__imp_GetProcessHeap
0x18001d1b8  mov     r8, rdi; lpMem
0x18001d1bb  xor     edx, edx; dwFlags
0x18001d1bd  mov     rcx, rax; hHeap
0x18001d1c0  call    cs:__imp_HeapSize
0x18001d1c6  lea     rcx, [rax-3]
0x18001d1ca  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x18001d1ce  ja      short loc_18001D1F1
0x18001d1d0  shr     rax, 1
0x18001d1d3  dec     rax
0x18001d1d6  cmp     rax, rbx
0x18001d1d9  jnb     short loc_18001D1E3
0x18001d1db  mov     rbx, rax
0x18001d1de  test    rax, rax
0x18001d1e1  jz      short loc_18001D1F1
0x18001d1e3  movzx   eax, r14w
0x18001d1e7  mov     rdi, [rbp+arg_10]
0x18001d1eb  mov     rcx, rbx
0x18001d1ee  rep stosw
0x18001d1f1  mov     rcx, [rbp+arg_10]; pv
0x18001d1f5  call    cs:__imp_CoTaskMemFree
0x18001d1fb  add     rsp, 40h
0x18001d1ff  pop     r14
0x18001d201  pop     rdi
0x18001d202  pop     rsi
0x18001d203  pop     rbx
0x18001d204  pop     rbp
0x18001d205  retn
```
