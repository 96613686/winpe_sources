# CreateTracingDirectoryA(x,x)

- ea: `0x1000471f`
- end: `0x1000495a`
- name: `_CreateTracingDirectoryA@8`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x10006fd6`

## callees

- `0x1000471f`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x100048d6`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x100048d6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10004793`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10004793`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1000475c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1000475c`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x10004776`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x10004776`
- `ntdll!RtlNtStatusToDosError` at `0x10004825`
- `ntdll!RtlNtStatusToDosError` at `0x10004825`
- `ntdll!NtCreateFile` at `0x100047fb`
- `ntdll!NtCreateFile` at `0x100047fb`
- `ntdll!RtlFreeHeap` at `0x1000481a`
- `ntdll!RtlFreeHeap` at `0x1000481a`
- `ntdll!RtlReleaseRelativeName` at `0x10004807`
- `ntdll!RtlReleaseRelativeName` at `0x10004807`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1000478a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1000478a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x100048ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10004913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x100048ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10004913`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10004887`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10004887`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10004880`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100048e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000490c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10004880`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100048e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000490c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10004947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10004947`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1000493f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1000493f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1000484f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1000484f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x1000486c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x100048a0`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x1000486c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x100048a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004923`

## pseudocode

```c
ULONG __fastcall CreateTracingDirectoryA(const CHAR *a1, void **a2)
{
  void **v2; // esi
  unsigned int v3; // kr00_4
  WCHAR *v4; // eax
  WCHAR *v5; // edi
  ULONG result; // eax
  BOOLEAN v7; // bl
  PWSTR Buffer; // ebx
  HANDLE ContainingDirectory; // eax
  int v10; // edi
  const char *v11; // ebx
  DWORD FinalPathNameByHandleA; // eax
  DWORD v13; // edi
  HANDLE ProcessHeap; // eax
  CHAR *v15; // esi
  DWORD v16; // eax
  int v17; // ecx
  HANDLE v18; // eax
  DWORD LastError; // edi
  HANDLE v20; // eax
  SIZE_T v22; // [esp-4h] [ebp-5Ch]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [esp+Ch] [ebp-4Ch] BYREF
  _RTL_RELATIVE_NAME_U DirectoryInfo; // [esp+24h] [ebp-34h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [esp+34h] [ebp-24h] BYREF
  _UNICODE_STRING NtPathName; // [esp+3Ch] [ebp-1Ch] BYREF
  int v27; // [esp+44h] [ebp-14h]
  HANDLE *v28; // [esp+48h] [ebp-10h]
  int v29; // [esp+4Ch] [ebp-Ch]
  LPCSTR lpFileName; // [esp+50h] [ebp-8h]
  char FileInformation; // [esp+57h] [ebp-1h] BYREF

  lpFileName = a1;
  v27 = 1;
  memset(&DirectoryInfo, 0, sizeof(DirectoryInfo));
  v2 = a2;
  v28 = a2;
  v29 = 0;
  v3 = strlen(a1);
  v4 = (WCHAR *)_malloc(2 * (v3 + 1));
  v5 = v4;
  if ( !v4 )
    return 8;
  __o_mbstowcs(v4, lpFileName, v3 + 1);
  v7 = RtlDosPathNameToNtPathName_U(v5, &NtPathName, 0, &DirectoryInfo);
  _free(v5);
  if ( !v7 )
    return 3;
  Buffer = NtPathName.Buffer;
  if ( DirectoryInfo.RelativeName.Length )
  {
    NtPathName = DirectoryInfo.RelativeName;
    ContainingDirectory = DirectoryInfo.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    DirectoryInfo.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.SecurityQualityOfService = 0;
  ObjectAttributes.Length = 24;
  ObjectAttributes.Attributes = 64;
  v10 = NtCreateFile(v2, 0xC0010000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 2u, 1u, 0, 0);
  RtlReleaseRelativeName(&DirectoryInfo);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v10 >= 0 )
  {
    v11 = lpFileName;
  }
  else
  {
    result = RtlNtStatusToDosError(v10);
    if ( result != 183 )
      return result;
    v11 = lpFileName;
    v27 = 0;
    *v2 = CreateFileA(lpFileName, 0xC0000000, 1u, 0, 3u, 0x2000000u, 0);
  }
  if ( *v2 == (void *)-1 || (FinalPathNameByHandleA = GetFinalPathNameByHandleA(*v2, 0, 0, 0)) == 0 )
  {
    LastError = GetLastError();
    goto LABEL_33;
  }
  v13 = FinalPathNameByHandleA + 1;
  v22 = FinalPathNameByHandleA + 1;
  ProcessHeap = GetProcessHeap();
  v15 = (CHAR *)HeapAlloc(ProcessHeap, 0, v22);
  if ( !v15 )
  {
    LastError = 8;
    goto LABEL_30;
  }
  v16 = GetFinalPathNameByHandleA(*v28, v15, v13, 0);
  if ( v16 )
  {
    if ( v16 >= 4 )
    {
      if ( *v15 != 92 || v15[1] != 92 || v15[2] != 63 || v15[3] != 92 )
      {
        v17 = 0;
        goto LABEL_24;
      }
      v29 = 4;
    }
    v17 = v29;
LABEL_24:
    if ( !__strnicmp(v11, &v15[v17], v16 - v17) )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v15);
      return 0;
    }
    LastError = 267;
    goto LABEL_29;
  }
  LastError = GetLastError();
LABEL_29:
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v15);
LABEL_30:
  v2 = v28;
LABEL_33:
  if ( v27 )
  {
    FileInformation = 1;
    SetFileInformationByHandle(*v2, FileDispositionInfo, &FileInformation, 1u);
  }
  CloseHandle(*v2);
  *v2 = (void *)-1;
  return LastError;
}

```

## disassembly

```asm
0x1000471f  mov     edi, edi
0x10004721  push    ebp
0x10004722  mov     ebp, esp
0x10004724  sub     esp, 4Ch
0x10004727  push    ebx
0x10004728  push    esi
0x10004729  push    edi
0x1000472a  xor     eax, eax
0x1000472c  mov     [ebp+lpFileName], ecx
0x1000472f  lea     edi, [ebp+DirectoryInfo]
0x10004732  mov     [ebp+var_14], 1
0x10004739  stosd
0x1000473a  mov     esi, edx
0x1000473c  mov     [ebp+var_10], esi
0x1000473f  lea     edx, [ecx+1]
0x10004742  mov     [ebp+var_C], 0
0x10004749  stosd
0x1000474a  stosd
0x1000474b  stosd
0x1000474c  mov     al, [ecx]
0x1000474e  inc     ecx
0x1000474f  test    al, al
0x10004751  jnz     short loc_1000474C
0x10004753  sub     ecx, edx
0x10004755  lea     ebx, [ecx+1]
0x10004758  lea     eax, [ebx+ebx]
0x1000475b  push    eax; Size
0x1000475c  call    ds:__imp__malloc
0x10004762  mov     edi, eax
0x10004764  pop     ecx
0x10004765  test    edi, edi
0x10004767  jnz     short loc_10004771
0x10004769  push    8
0x1000476b  pop     eax
0x1000476c  jmp     loc_10004955
0x10004771  push    ebx
0x10004772  push    [ebp+lpFileName]
0x10004775  push    edi
0x10004776  call    ds:__imp___o_mbstowcs
0x1000477c  add     esp, 0Ch
0x1000477f  lea     eax, [ebp+DirectoryInfo]
0x10004782  push    eax; DirectoryInfo
0x10004783  push    0; NtFileNamePart
0x10004785  lea     eax, [ebp+NtPathName]
0x10004788  push    eax; NtPathName
0x10004789  push    edi; DosPathName
0x1000478a  call    ds:__imp__RtlDosPathNameToNtPathName_U@16; RtlDosPathNameToNtPathName_U(x,x,x,x)
0x10004790  push    edi; Block
0x10004791  mov     bl, al
0x10004793  call    ds:__imp__free
0x10004799  pop     ecx
0x1000479a  test    bl, bl
0x1000479c  jnz     short loc_100047A2
0x1000479e  push    3
0x100047a0  jmp     short loc_1000476B
0x100047a2  mov     ecx, dword ptr [ebp+DirectoryInfo.RelativeName.Length]
0x100047a5  mov     ebx, [ebp+NtPathName.Buffer]
0x100047a8  test    cx, cx
0x100047ab  jz      short loc_100047BB
0x100047ad  mov     eax, [ebp+DirectoryInfo.RelativeName.Buffer]
0x100047b0  mov     [ebp+NtPathName.Buffer], eax
0x100047b3  mov     eax, [ebp+DirectoryInfo.ContainingDirectory]
0x100047b6  mov     dword ptr [ebp+NtPathName.Length], ecx
0x100047b9  jmp     short loc_100047C0
0x100047bb  xor     eax, eax
0x100047bd  mov     [ebp+DirectoryInfo.ContainingDirectory], eax
0x100047c0  mov     [ebp+ObjectAttributes.RootDirectory], eax
0x100047c3  lea     eax, [ebp+NtPathName]
0x100047c6  mov     [ebp+ObjectAttributes.ObjectName], eax
0x100047c9  xor     eax, eax
0x100047cb  push    eax; EaLength
0x100047cc  push    eax; EaBuffer
0x100047cd  push    1; CreateOptions
0x100047cf  push    2; CreateDisposition
0x100047d1  push    1; ShareAccess
0x100047d3  push    80h; FileAttributes
0x100047d8  push    eax; AllocationSize
0x100047d9  mov     [ebp+ObjectAttributes.SecurityDescriptor], eax
0x100047dc  mov     [ebp+ObjectAttributes.SecurityQualityOfService], eax
0x100047df  lea     eax, [ebp+IoStatusBlock]
0x100047e2  push    eax; IoStatusBlock
0x100047e3  lea     eax, [ebp+ObjectAttributes]
0x100047e6  mov     [ebp+ObjectAttributes.Length], 18h
0x100047ed  push    eax; ObjectAttributes
0x100047ee  push    0C0010000h; DesiredAccess
0x100047f3  push    esi; FileHandle
0x100047f4  mov     [ebp+ObjectAttributes.Attributes], 40h ; '@'
0x100047fb  call    ds:__imp__NtCreateFile@44; NtCreateFile(x,x,x,x,x,x,x,x,x,x,x)
0x10004801  mov     edi, eax
0x10004803  lea     eax, [ebp+DirectoryInfo]
0x10004806  push    eax; RelativeName
0x10004807  call    ds:__imp__RtlReleaseRelativeName@4; RtlReleaseRelativeName(x)
0x1000480d  mov     ecx, large fs:30h
0x10004814  push    ebx; P
0x10004815  push    0; Flags
0x10004817  push    dword ptr [ecx+18h]; HeapHandle
0x1000481a  call    ds:__imp__RtlFreeHeap@12; RtlFreeHeap(x,x,x)
0x10004820  test    edi, edi
0x10004822  jns     short loc_10004859
0x10004824  push    edi; Status
0x10004825  call    ds:__imp__RtlNtStatusToDosError@4; RtlNtStatusToDosError(x)
0x1000482b  cmp     eax, 0B7h
0x10004830  jnz     loc_10004955
0x10004836  mov     ebx, [ebp+lpFileName]
0x10004839  xor     edi, edi
0x1000483b  push    edi; hTemplateFile
0x1000483c  push    2000000h; dwFlagsAndAttributes
0x10004841  push    3; dwCreationDisposition
0x10004843  push    edi; lpSecurityAttributes
0x10004844  push    1; dwShareMode
0x10004846  push    0C0000000h; dwDesiredAccess
0x1000484b  push    ebx; lpFileName
0x1000484c  mov     [ebp+var_14], edi
0x1000484f  call    ds:__imp__CreateFileA@28; CreateFileA(x,x,x,x,x,x,x)
0x10004855  mov     [esi], eax
0x10004857  jmp     short loc_1000485E
0x10004859  mov     ebx, [ebp+lpFileName]
0x1000485c  xor     edi, edi
0x1000485e  cmp     dword ptr [esi], 0FFFFFFFFh
0x10004861  jz      loc_10004923
0x10004867  push    edi; dwFlags
0x10004868  push    edi; cchFilePath
0x10004869  push    edi; lpszFilePath
0x1000486a  push    dword ptr [esi]; hFile
0x1000486c  call    ds:__imp__GetFinalPathNameByHandleA@16; GetFinalPathNameByHandleA(x,x,x,x)
0x10004872  mov     edi, eax
0x10004874  test    edi, edi
0x10004876  jz      loc_10004923
0x1000487c  inc     edi
0x1000487d  push    edi; dwBytes
0x1000487e  push    0; dwFlags
0x10004880  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10004886  push    eax; hHeap
0x10004887  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x1000488d  mov     esi, eax
0x1000488f  test    esi, esi
0x10004891  jz      loc_1000491E
0x10004897  mov     eax, [ebp+var_10]
0x1000489a  push    0; dwFlags
0x1000489c  push    edi; cchFilePath
0x1000489d  push    esi; lpszFilePath
0x1000489e  push    dword ptr [eax]; hFile
0x100048a0  call    ds:__imp__GetFinalPathNameByHandleA@16; GetFinalPathNameByHandleA(x,x,x,x)
0x100048a6  test    eax, eax
0x100048a8  jz      short loc_10004901
0x100048aa  push    4
0x100048ac  pop     ecx
0x100048ad  cmp     eax, ecx
0x100048af  jb      short loc_100048CB
0x100048b1  cmp     byte ptr [esi], 5Ch ; '\'
0x100048b4  jnz     short loc_100048F6
0x100048b6  cmp     byte ptr [esi+1], 5Ch ; '\'
0x100048ba  jnz     short loc_100048F6
0x100048bc  cmp     byte ptr [esi+2], 3Fh ; '?'
0x100048c0  jnz     short loc_100048F6
0x100048c2  cmp     byte ptr [esi+3], 5Ch ; '\'
0x100048c6  jnz     short loc_100048F6
0x100048c8  mov     [ebp+var_C], ecx
0x100048cb  mov     ecx, [ebp+var_C]
0x100048ce  sub     eax, ecx
0x100048d0  push    eax; MaxCount
0x100048d1  lea     eax, [ecx+esi]
0x100048d4  push    eax; String2
0x100048d5  push    ebx; String1
0x100048d6  call    ds:__imp___strnicmp
0x100048dc  add     esp, 0Ch
0x100048df  test    eax, eax
0x100048e1  jnz     short loc_100048FA
0x100048e3  push    esi; lpMem
0x100048e4  push    eax; dwFlags
0x100048e5  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x100048eb  push    eax; hHeap
0x100048ec  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x100048f2  xor     eax, eax
0x100048f4  jmp     short loc_10004955
0x100048f6  xor     ecx, ecx
0x100048f8  jmp     short loc_100048CE
0x100048fa  mov     edi, 10Bh
0x100048ff  jmp     short loc_10004909
0x10004901  call    ds:__imp__GetLastError@0; GetLastError()
0x10004907  mov     edi, eax
0x10004909  push    esi; lpMem
0x1000490a  push    0; dwFlags
0x1000490c  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10004912  push    eax; hHeap
0x10004913  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10004919  mov     esi, [ebp+var_10]
0x1000491c  jmp     short loc_1000492B
0x1000491e  push    8
0x10004920  pop     edi
0x10004921  jmp     short loc_10004919
0x10004923  call    ds:__imp__GetLastError@0; GetLastError()
0x10004929  mov     edi, eax
0x1000492b  cmp     [ebp+var_14], 0
0x1000492f  jz      short loc_10004945
0x10004931  push    1; dwBufferSize
0x10004933  lea     eax, [ebp+FileInformation]
0x10004936  mov     [ebp+FileInformation], 1
0x1000493a  push    eax; lpFileInformation
0x1000493b  push    4; FileInformationClass
0x1000493d  push    dword ptr [esi]; hFile
0x1000493f  call    ds:__imp__SetFileInformationByHandle@16; SetFileInformationByHandle(x,x,x,x)
0x10004945  push    dword ptr [esi]; hObject
0x10004947  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000494d  mov     dword ptr [esi], 0FFFFFFFFh
0x10004953  mov     eax, edi
0x10004955  pop     edi
0x10004956  pop     esi
0x10004957  pop     ebx
0x10004958  leave
0x10004959  retn
```
