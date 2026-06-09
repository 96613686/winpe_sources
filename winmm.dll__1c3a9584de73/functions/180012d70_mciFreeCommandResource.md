# mciFreeCommandResource

- ea: `0x180012d70`
- end: `0x180012ec9`
- name: `mciFreeCommandResource`
- size: `345`
- prototype: `BOOL __stdcall(UINT wTable)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014b54`

## callees

- `0x18000b1f8`
- `0x180012d70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012dcc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012dcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012e09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012e63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012e09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012e63`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012e71`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012e71`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x180012e3f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x180012e3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e51`

## pseudocode

```c
BOOL __stdcall mciFreeCommandResource(UINT wTable)
{
  __int64 v1; // rsi
  unsigned int i; // ecx
  __int64 v3; // rdx
  __int64 v5; // rdi
  void *v6; // rcx
  void *v7; // rbx
  HMODULE v8; // rbx
  __int64 v9; // r9

  v1 = wTable;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids, wTable);
  }
  if ( (_DWORD)v1 == -1 || (unsigned int)v1 >= number_of_command_tables )
    return 0;
  EnterCriticalSection(&mciCritSec);
  for ( i = 1; i < MCI_wNextDeviceID; ++i )
  {
    v3 = *((_QWORD *)MCI_lpDeviceList + i);
    if ( v3 && (*(_DWORD *)(v3 + 64) == (_DWORD)v1 || *(_DWORD *)(v3 + 60) == (_DWORD)v1) )
    {
      LeaveCriticalSection(&mciCritSec);
      return 0;
    }
  }
  v5 = 5 * v1;
  v6 = (void *)command_tables[5 * v1];
  v7 = (void *)command_tables[5 * v1 + 3];
  command_tables[v5] = 0;
  command_tables[v5 + 3] = 0;
  LODWORD(command_tables[v5 + 2]) = 0;
  FreeResource(v6);
  HeapFree(hHeap, 0, v7);
  v8 = (HMODULE)command_tables[5 * v1 + 1];
  LeaveCriticalSection(&mciCritSec);
  if ( v8 )
    FreeLibrary(v8);
  v9 = number_of_command_tables;
  if ( (_DWORD)v1 == number_of_command_tables - 1 )
    v9 = --number_of_command_tables;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids, v9);
  }
  return 1;
}

```

## disassembly

```asm
0x180012d70  push    rbx
0x180012d72  push    rsi
0x180012d73  push    rdi
0x180012d74  push    r13
0x180012d76  push    r14
0x180012d78  sub     rsp, 20h
0x180012d7c  mov     esi, ecx
0x180012d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d85  lea     r13, WPP_GLOBAL_Control
0x180012d8c  cmp     rcx, r13
0x180012d8f  jz      short loc_180012DB8
0x180012d91  test    dword ptr [rcx+1Ch], 400000h
0x180012d98  jz      short loc_180012DB8
0x180012d9a  cmp     byte ptr [rcx+19h], 3
0x180012d9e  jb      short loc_180012DB8
0x180012da0  mov     rcx, [rcx+10h]
0x180012da4  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180012dab  mov     edx, 1Ah
0x180012db0  mov     r9d, esi
0x180012db3  call    WPP_SF_d
0x180012db8  cmp     esi, 0FFFFFFFFh
0x180012dbb  jz      short loc_180012E0F
0x180012dbd  cmp     esi, cs:?number_of_command_tables@@3IA; uint number_of_command_tables
0x180012dc3  jnb     short loc_180012E0F
0x180012dc5  lea     rcx, mciCritSec; lpCriticalSection
0x180012dcc  call    cs:__imp_EnterCriticalSection
0x180012dd2  mov     r8, cs:MCI_lpDeviceList
0x180012dd9  mov     ecx, 1
0x180012dde  xor     r9d, r9d
0x180012de1  cmp     ecx, cs:MCI_wNextDeviceID
0x180012de7  jnb     short loc_180012E1D
0x180012de9  mov     eax, ecx
0x180012deb  mov     rdx, [r8+rax*8]
0x180012def  test    rdx, rdx
0x180012df2  jz      short loc_180012DFE
0x180012df4  cmp     [rdx+40h], esi
0x180012df7  jz      short loc_180012E02
0x180012df9  cmp     [rdx+3Ch], esi
0x180012dfc  jz      short loc_180012E02
0x180012dfe  inc     ecx
0x180012e00  jmp     short loc_180012DE1
0x180012e02  lea     rcx, mciCritSec; lpCriticalSection
0x180012e09  call    cs:__imp_LeaveCriticalSection
0x180012e0f  xor     eax, eax
0x180012e11  add     rsp, 20h
0x180012e15  pop     r14
0x180012e17  pop     r13
0x180012e19  pop     rdi
0x180012e1a  pop     rsi
0x180012e1b  pop     rbx
0x180012e1c  retn
0x180012e1d  lea     rdi, [rsi+rsi*4]
0x180012e21  lea     r14, command_tables
0x180012e28  mov     rcx, [r14+rdi*8]; hResData
0x180012e2c  mov     rbx, [r14+rdi*8+18h]
0x180012e31  mov     [r14+rdi*8], r9
0x180012e35  mov     [r14+rdi*8+18h], r9
0x180012e3a  mov     [r14+rdi*8+10h], r9d
0x180012e3f  call    cs:__imp_FreeResource
0x180012e45  mov     rcx, cs:hHeap; hHeap
0x180012e4c  mov     r8, rbx; lpMem
0x180012e4f  xor     edx, edx; dwFlags
0x180012e51  call    cs:__imp_HeapFree
0x180012e57  mov     rbx, [r14+rdi*8+8]
0x180012e5c  lea     rcx, mciCritSec; lpCriticalSection
0x180012e63  call    cs:__imp_LeaveCriticalSection
0x180012e69  test    rbx, rbx
0x180012e6c  jz      short loc_180012E77
0x180012e6e  mov     rcx, rbx; hLibModule
0x180012e71  call    cs:__imp_FreeLibrary
0x180012e77  mov     r9d, cs:?number_of_command_tables@@3IA; uint number_of_command_tables
0x180012e7e  lea     eax, [r9-1]
0x180012e82  cmp     esi, eax
0x180012e84  jnz     short loc_180012E8F
0x180012e86  mov     r9d, eax
0x180012e89  mov     cs:?number_of_command_tables@@3IA, eax; uint number_of_command_tables
0x180012e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e96  cmp     rcx, r13
0x180012e99  jz      short loc_180012EBF
0x180012e9b  test    dword ptr [rcx+1Ch], 400000h
0x180012ea2  jz      short loc_180012EBF
0x180012ea4  cmp     byte ptr [rcx+19h], 3
0x180012ea8  jb      short loc_180012EBF
0x180012eaa  mov     rcx, [rcx+10h]
0x180012eae  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180012eb5  mov     edx, 1Eh
0x180012eba  call    WPP_SF_d
0x180012ebf  mov     eax, 1
0x180012ec4  jmp     loc_180012E11
```
