# windiag::read_file_bytes(char const *,std::vector<uchar,std::allocator<uchar>> &,__int64)

- ea: `0x18007902c`
- end: `0x180079173`
- name: `?read_file_bytes@windiag@@YA_NPEBDAEAV?$vector@EV?$allocator@E@std@@@std@@_J@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180075fa0`

## callees

- `0x180004510`
- `0x180041564`
- `0x1800416a0`
- `0x1800511ac`
- `0x18007902c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079138`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079138`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079148`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180079114`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180079114`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800790c5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800790c5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180079092`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180079092`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall windiag::read_file_bytes(__int64 a1, __int64 a2)
{
  char v3; // si
  __int64 v4; // rax
  HANDLE FileW; // rbx
  DWORD v6; // ecx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-48h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-40h] BYREF
  HANDLE v10; // [rsp+50h] [rbp-38h]
  _BYTE v11[32]; // [rsp+58h] [rbp-30h] BYREF

  v3 = 0;
  v4 = windiag::char_to_wstring(v11, a1);
  if ( *(_QWORD *)(v4 + 24) > 7u )
    v4 = *(_QWORD *)v4;
  FileW = CreateFileW((LPCWSTR)v4, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v10 = FileW;
  std::wstring::~wstring(v11);
  if ( FileW != (HANDLE)-1LL )
  {
    FileSize.QuadPart = 0;
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      if ( FileSize.QuadPart >= 0 )
      {
        if ( FileSize.QuadPart <= 0x100000 )
        {
          std::vector<unsigned char>::resize(a2);
          NumberOfBytesRead = 0;
          if ( ReadFile(FileW, *(LPVOID *)a2, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2, &NumberOfBytesRead, 0)
            && NumberOfBytesRead == *(_QWORD *)(a2 + 8) - *(_QWORD *)a2 )
          {
            v3 = 1;
            goto LABEL_13;
          }
          v6 = 234;
        }
        else
        {
          v6 = 1784;
        }
        SetLastError(v6);
      }
    }
  }
LABEL_13:
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return v3;
}

```

## disassembly

```asm
0x18007902c  mov     [rsp+arg_10], rbx
0x180079031  mov     [rsp+arg_18], rsi
0x180079036  push    rdi
0x180079037  sub     rsp, 80h
0x18007903e  mov     rax, cs:__security_cookie
0x180079045  xor     rax, rsp
0x180079048  mov     [rsp+88h+var_10], rax
0x18007904d  mov     rdi, rdx
0x180079050  xor     sil, sil
0x180079053  mov     rdx, rcx
0x180079056  lea     rcx, [rsp+88h+var_30]
0x18007905b  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x180079060  cmp     qword ptr [rax+18h], 7
0x180079065  jbe     short loc_18007906A
0x180079067  mov     rax, [rax]
0x18007906a  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x180079073  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18007907b  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180079083  xor     r9d, r9d; lpSecurityAttributes
0x180079086  mov     edx, 80000000h; dwDesiredAccess
0x18007908b  lea     r8d, [r9+1]; dwShareMode
0x18007908f  mov     rcx, rax; lpFileName
0x180079092  call    cs:__imp_CreateFileW
0x180079098  mov     rbx, rax
0x18007909b  mov     [rsp+88h+var_38], rax
0x1800790a0  lea     rcx, [rsp+88h+var_30]
0x1800790a5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800790aa  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800790ae  jz      loc_18007913F
0x1800790b4  mov     qword ptr [rsp+88h+FileSize], 0
0x1800790bd  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x1800790c2  mov     rcx, rbx; hFile
0x1800790c5  call    cs:__imp_GetFileSizeEx
0x1800790cb  test    eax, eax
0x1800790cd  jz      short loc_18007913F
0x1800790cf  mov     rdx, qword ptr [rsp+88h+FileSize]
0x1800790d4  test    rdx, rdx
0x1800790d7  js      short loc_18007913F
0x1800790d9  cmp     rdx, 100000h
0x1800790e0  jle     short loc_1800790E9
0x1800790e2  mov     ecx, 6F8h
0x1800790e7  jmp     short loc_180079138
0x1800790e9  mov     rcx, rdi
0x1800790ec  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800790f1  mov     [rsp+88h+NumberOfBytesRead], 0
0x1800790f9  mov     r8d, [rdi+8]
0x1800790fd  sub     r8d, [rdi]; nNumberOfBytesToRead
0x180079100  mov     qword ptr [rsp+88h+dwCreationDisposition], 0; lpOverlapped
0x180079109  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18007910e  mov     rdx, [rdi]; lpBuffer
0x180079111  mov     rcx, rbx; hFile
0x180079114  call    cs:__imp_ReadFile
0x18007911a  test    eax, eax
0x18007911c  jz      short loc_180079133
0x18007911e  mov     rcx, [rdi+8]
0x180079122  sub     rcx, [rdi]
0x180079125  mov     eax, [rsp+88h+NumberOfBytesRead]
0x180079129  cmp     rax, rcx
0x18007912c  jnz     short loc_180079133
0x18007912e  mov     sil, 1
0x180079131  jmp     short loc_18007913F
0x180079133  mov     ecx, 0EAh; dwErrCode
0x180079138  call    cs:__imp_SetLastError
0x18007913e  nop
0x18007913f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180079143  jz      short loc_18007914E
0x180079145  mov     rcx, rbx; hObject
0x180079148  call    cs:__imp_CloseHandle
0x18007914e  mov     al, sil
0x180079151  mov     rcx, [rsp+88h+var_10]
0x180079156  xor     rcx, rsp; StackCookie
0x180079159  call    __security_check_cookie
0x18007915e  lea     r11, [rsp+88h+var_8]
0x180079166  mov     rbx, [r11+20h]
0x18007916a  mov     rsi, [r11+28h]
0x18007916e  mov     rsp, r11
0x180079171  pop     rdi
0x180079172  retn
```
