# MergeSdbp_GetRedirectedSdbPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)

- ea: `0x140023334`
- end: `0x14002344f`
- name: `?MergeSdbp_GetRedirectedSdbPath@@YA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `283`
- prototype: `bool __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140024958`

## callees

- `0x140015eb4`
- `0x140020f9c`
- `0x140023334`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002335d`
- `KERNEL32!GetLastError` at `0x1400233cf`
- `KERNEL32!GetLastError` at `0x14002335d`
- `KERNEL32!GetLastError` at `0x1400233cf`
- `KERNEL32!GetProcessHeap` at `0x140023365`
- `KERNEL32!GetProcessHeap` at `0x1400233d7`
- `KERNEL32!GetProcessHeap` at `0x140023404`
- `KERNEL32!GetProcessHeap` at `0x140023365`
- `KERNEL32!GetProcessHeap` at `0x1400233d7`
- `KERNEL32!GetProcessHeap` at `0x140023404`
- `KERNEL32!SetLastError` at `0x14002337b`
- `KERNEL32!SetLastError` at `0x1400233ed`
- `KERNEL32!SetLastError` at `0x14002337b`
- `KERNEL32!SetLastError` at `0x1400233ed`
- `KERNEL32!HeapFree` at `0x140023373`
- `KERNEL32!HeapFree` at `0x1400233e5`
- `KERNEL32!HeapFree` at `0x140023412`
- `KERNEL32!HeapFree` at `0x140023373`
- `KERNEL32!HeapFree` at `0x1400233e5`
- `KERNEL32!HeapFree` at `0x140023412`
- `ntdll!RtlFreeHeap` at `0x14002342f`
- `ntdll!RtlFreeHeap` at `0x14002342f`

## pseudocode

```c
bool __fastcall MergeSdbp_GetRedirectedSdbPath(void **a1, __int64 a2)
{
  void *v2; // rsi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  PVOID v7; // rsi
  void *v8; // rbp
  void *v9; // r14
  DWORD v10; // ebx
  HANDLE v11; // rax
  void *v12; // rbx
  HANDLE v13; // rax
  _QWORD v15[5]; // [rsp+20h] [rbp-28h] BYREF
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a1;
  P = 0;
  if ( v2 )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    SetLastError(LastError);
  }
  *a1 = 0;
  if ( (int)SdbGetMergeRedirectPath(&P, 0, 0, a2) >= 0 )
  {
    v7 = P;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      v15,
      P,
      -1);
    if ( a1 == v15 )
    {
      v12 = (void *)v15[0];
    }
    else
    {
      v8 = *a1;
      v9 = (void *)v15[0];
      if ( *a1 )
      {
        v10 = GetLastError();
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v8);
        SetLastError(v10);
      }
      *a1 = v9;
      v12 = 0;
    }
    if ( v12 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v12);
    }
    if ( v7 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  }
  return *a1 != 0;
}

```

## disassembly

```asm
0x140023334  mov     [rsp+arg_8], rbx
0x140023339  mov     [rsp+arg_10], rbp
0x14002333e  push    rsi
0x14002333f  push    rdi
0x140023340  push    r14
0x140023342  sub     rsp, 30h
0x140023346  mov     rsi, [rcx]
0x140023349  mov     rbp, rdx
0x14002334c  mov     [rsp+48h+P], 0
0x140023355  mov     rdi, rcx
0x140023358  test    rsi, rsi
0x14002335b  jz      short loc_140023381
0x14002335d  call    cs:__imp_GetLastError
0x140023363  mov     ebx, eax
0x140023365  call    cs:__imp_GetProcessHeap
0x14002336b  mov     r8, rsi; lpMem
0x14002336e  xor     edx, edx; dwFlags
0x140023370  mov     rcx, rax; hHeap
0x140023373  call    cs:__imp_HeapFree
0x140023379  mov     ecx, ebx; dwErrCode
0x14002337b  call    cs:__imp_SetLastError
0x140023381  mov     r9, rbp
0x140023384  mov     qword ptr [rdi], 0
0x14002338b  xor     r8d, r8d
0x14002338e  lea     rcx, [rsp+48h+P]
0x140023393  xor     edx, edx
0x140023395  call    SdbGetMergeRedirectPath
0x14002339a  test    eax, eax
0x14002339c  js      loc_140023435
0x1400233a2  mov     rsi, [rsp+48h+P]
0x1400233a7  lea     rcx, [rsp+48h+var_28]
0x1400233ac  mov     rdx, rsi
0x1400233af  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400233b3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1400233b8  lea     rax, [rsp+48h+var_28]
0x1400233bd  cmp     rdi, rax
0x1400233c0  jz      short loc_1400233FA
0x1400233c2  mov     rbp, [rdi]
0x1400233c5  mov     r14, [rsp+48h+var_28]
0x1400233ca  test    rbp, rbp
0x1400233cd  jz      short loc_1400233F3
0x1400233cf  call    cs:__imp_GetLastError
0x1400233d5  mov     ebx, eax
0x1400233d7  call    cs:__imp_GetProcessHeap
0x1400233dd  mov     r8, rbp; lpMem
0x1400233e0  xor     edx, edx; dwFlags
0x1400233e2  mov     rcx, rax; hHeap
0x1400233e5  call    cs:__imp_HeapFree
0x1400233eb  mov     ecx, ebx; dwErrCode
0x1400233ed  call    cs:__imp_SetLastError
0x1400233f3  mov     [rdi], r14
0x1400233f6  xor     ebx, ebx
0x1400233f8  jmp     short loc_1400233FF
0x1400233fa  mov     rbx, [rsp+48h+var_28]
0x1400233ff  test    rbx, rbx
0x140023402  jz      short loc_140023418
0x140023404  call    cs:__imp_GetProcessHeap
0x14002340a  mov     r8, rbx; lpMem
0x14002340d  xor     edx, edx; dwFlags
0x14002340f  mov     rcx, rax; hHeap
0x140023412  call    cs:__imp_HeapFree
0x140023418  test    rsi, rsi
0x14002341b  jz      short loc_140023435
0x14002341d  mov     rcx, gs:60h
0x140023426  mov     r8, rsi; P
0x140023429  xor     edx, edx; Flags
0x14002342b  mov     rcx, [rcx+30h]; HeapHandle
0x14002342f  call    cs:__imp_RtlFreeHeap
0x140023435  cmp     qword ptr [rdi], 0
0x140023439  mov     rbx, [rsp+48h+arg_8]
0x14002343e  mov     rbp, [rsp+48h+arg_10]
0x140023443  setnz   al
0x140023446  add     rsp, 30h
0x14002344a  pop     r14
0x14002344c  pop     rdi
0x14002344d  pop     rsi
0x14002344e  retn
```
