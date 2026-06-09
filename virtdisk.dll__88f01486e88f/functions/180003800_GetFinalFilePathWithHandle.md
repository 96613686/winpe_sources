# GetFinalFilePathWithHandle

- ea: `0x180003800`
- end: `0x18000392a`
- name: `GetFinalFilePathWithHandle`
- size: `298`
- prototype: `__int64 __fastcall(HANDLE hFile, PVOID *, _DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x180002740`
- `0x180004560`
- `0x180004f60`

## callees

- `0x180003800`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180003884`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180003884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038b0`
- `ntdll!RtlFreeHeap` at `0x1800038df`
- `ntdll!RtlFreeHeap` at `0x1800038df`
- `ntdll!RtlAllocateHeap` at `0x180003853`
- `ntdll!RtlAllocateHeap` at `0x180003853`

## pseudocode

```c
__int64 __fastcall GetFinalFilePathWithHandle(HANDLE hFile, PVOID *a2, _DWORD *a3)
{
  PVOID ProcessHeap; // rcx
  PVOID Heap; // rax
  unsigned int v8; // ebx
  unsigned int i; // ebx
  DWORD FinalPathNameByHandleW; // eax
  DWORD LastError; // eax
  __int64 result; // rax
  int v13; // r8d
  unsigned int v14; // edx
  DWORD dwFlags[18]; // [rsp+20h] [rbp-48h]

  dwFlags[0] = 0;
  dwFlags[1] = 1;
  dwFlags[2] = 8;
  dwFlags[3] = 9;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  dwFlags[4] = 10;
  Heap = RtlAllocateHeap(ProcessHeap, 8u, 0xFFFEu);
  *a2 = Heap;
  if ( !Heap )
  {
    v8 = 14;
LABEL_12:
    if ( *a2 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a2);
      *a2 = 0;
      *a3 = 0;
    }
    return v8;
  }
  for ( i = 0; i < 5; ++i )
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, (LPWSTR)*a2, 0x7FFFu, dwFlags[i]);
    *a3 = FinalPathNameByHandleW;
    if ( FinalPathNameByHandleW )
      break;
  }
  if ( FinalPathNameByHandleW > 0x7FFF )
  {
    v8 = 2;
    goto LABEL_12;
  }
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 2;
    v8 = LastError;
    goto LABEL_12;
  }
  v13 = -1;
  v14 = -1;
  if ( FinalPathNameByHandleW + 1 >= FinalPathNameByHandleW )
    v14 = FinalPathNameByHandleW + 1;
  if ( 2 * (unsigned __int64)v14 <= 0xFFFFFFFF )
    v13 = 2 * v14;
  result = 0;
  *a3 = v13;
  return result;
}

```

## disassembly

```asm
0x180003800  push    rbx
0x180003802  push    rsi
0x180003803  push    rdi
0x180003804  push    r14
0x180003806  sub     rsp, 48h
0x18000380a  mov     rsi, rcx
0x18000380d  mov     [rsp+68h+dwFlags], 0
0x180003815  mov     rcx, gs:60h
0x18000381e  mov     r14, r8
0x180003821  mov     rdi, rdx
0x180003824  mov     [rsp+68h+var_44], 1
0x18000382c  mov     edx, 8; Flags
0x180003831  mov     [rsp+68h+var_40], 8
0x180003839  mov     r8d, 0FFFEh; Size
0x18000383f  mov     [rsp+68h+var_3C], 9
0x180003847  mov     rcx, [rcx+30h]; HeapHandle
0x18000384b  mov     [rsp+68h+var_38], 0Ah
0x180003853  call    cs:__imp_RtlAllocateHeap
0x18000385a  nop     dword ptr [rax+rax+00h]
0x18000385f  mov     [rdi], rax
0x180003862  test    rax, rax
0x180003865  jnz     short loc_18000386E
0x180003867  mov     ebx, 0Eh
0x18000386c  jmp     short loc_1800038C8
0x18000386e  xor     ebx, ebx
0x180003870  mov     rdx, [rdi]; lpszFilePath
0x180003873  mov     r8d, 7FFFh; cchFilePath
0x180003879  movsxd  r9, ebx
0x18000387c  mov     rcx, rsi; hFile
0x18000387f  mov     r9d, [rsp+r9*4+68h+dwFlags]; dwFlags
0x180003884  call    cs:__imp_GetFinalPathNameByHandleW
0x18000388b  nop     dword ptr [rax+rax+00h]
0x180003890  mov     [r14], eax
0x180003893  test    eax, eax
0x180003895  jnz     short loc_18000389E
0x180003897  inc     ebx
0x180003899  cmp     ebx, 5
0x18000389c  jb      short loc_180003870
0x18000389e  cmp     eax, 7FFFh
0x1800038a3  jbe     short loc_1800038AC
0x1800038a5  mov     ebx, 2
0x1800038aa  jmp     short loc_1800038C8
0x1800038ac  test    eax, eax
0x1800038ae  jnz     short loc_1800038FD
0x1800038b0  call    cs:__imp_GetLastError
0x1800038b7  nop     dword ptr [rax+rax+00h]
0x1800038bc  mov     ebx, 2
0x1800038c1  test    eax, eax
0x1800038c3  cmovz   eax, ebx
0x1800038c6  mov     ebx, eax
0x1800038c8  mov     r8, [rdi]; P
0x1800038cb  test    r8, r8
0x1800038ce  jz      short loc_1800038F9
0x1800038d0  mov     rcx, gs:60h
0x1800038d9  xor     edx, edx; Flags
0x1800038db  mov     rcx, [rcx+30h]; HeapHandle
0x1800038df  call    cs:__imp_RtlFreeHeap
0x1800038e6  nop     dword ptr [rax+rax+00h]
0x1800038eb  mov     qword ptr [rdi], 0
0x1800038f2  mov     dword ptr [r14], 0
0x1800038f9  mov     eax, ebx
0x1800038fb  jmp     short loc_18000391F
0x1800038fd  lea     ecx, [rax+1]
0x180003900  mov     r8d, 0FFFFFFFFh
0x180003906  cmp     ecx, eax
0x180003908  mov     edx, r8d
0x18000390b  cmovnb  edx, ecx
0x18000390e  mov     eax, edx
0x180003910  add     rax, rax
0x180003913  cmp     rax, r8
0x180003916  cmovbe  r8d, eax
0x18000391a  xor     eax, eax
0x18000391c  mov     [r14], r8d
0x18000391f  add     rsp, 48h
0x180003923  pop     r14
0x180003925  pop     rdi
0x180003926  pop     rsi
0x180003927  pop     rbx
0x180003928  retn
```
