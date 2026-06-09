# MgdReadChunkHandle(W3_MGD_HANDLER *,void *,unsigned __int64,ulong *,uchar *)

- ea: `0x18005a9f0`
- end: `0x18005abc7`
- name: `?MgdReadChunkHandle@@YAJPEAVW3_MGD_HANDLER@@PEAX_KPEAKPEAE@Z`
- size: `471`
- prototype: `__int64 __fastcall(struct W3_MGD_HANDLER *, void *, __int64, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x18005a9f0`
- `0x1800616d8`
- `0x1800653ba`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18005aae7`
- `KERNEL32!ReadFile` at `0x18005aae7`
- `KERNEL32!CloseHandle` at `0x18005aba4`
- `KERNEL32!CloseHandle` at `0x18005aba4`
- `KERNEL32!GetLastError` at `0x18005aaf1`
- `KERNEL32!GetLastError` at `0x18005ab22`
- `KERNEL32!GetLastError` at `0x18005ab88`
- `KERNEL32!GetLastError` at `0x18005aaf1`
- `KERNEL32!GetLastError` at `0x18005ab22`
- `KERNEL32!GetLastError` at `0x18005ab88`
- `KERNEL32!GetOverlappedResult` at `0x18005ab18`
- `KERNEL32!GetOverlappedResult` at `0x18005ab18`
- `KERNEL32!CreateEventW` at `0x18005aa79`
- `KERNEL32!CreateEventW` at `0x18005aa79`

## pseudocode

```c
__int64 __fastcall MgdReadChunkHandle(
        struct W3_MGD_HANDLER *a1,
        void *a2,
        __int64 a3,
        unsigned int *a4,
        unsigned __int8 *a5)
{
  unsigned int v5; // esi
  unsigned int v6; // r14d
  void *v8; // rdi
  unsigned __int8 *v9; // rbx
  HANDLE EventW; // rax
  unsigned int v11; // r12d
  void *v12; // r13
  unsigned __int64 v13; // r9
  unsigned int v14; // ecx
  DWORD LastError; // eax
  DWORD v16; // edi
  signed int v17; // eax
  unsigned __int64 v19; // [rsp+30h] [rbp-38h]
  __int64 v20; // [rsp+38h] [rbp-30h]
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-28h] BYREF
  DWORD NumberOfBytesRead; // [rsp+B0h] [rbp+48h] BYREF
  void *v23; // [rsp+B8h] [rbp+50h]
  __int64 v24; // [rsp+C0h] [rbp+58h]
  unsigned __int8 *ChunkBuffer; // [rsp+C8h] [rbp+60h]

  v24 = a3;
  v23 = a2;
  v5 = 0;
  v6 = 0;
  v8 = a2;
  if ( a1 && *((_DWORD *)a1 + 4) == 809840692 && a2 != (void *)-1LL && a5 && a4 && *a4 )
  {
    ChunkBuffer = W3_MGD_HANDLER::GetReadChunkBuffer(a1);
    v9 = ChunkBuffer;
    if ( ChunkBuffer )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      v11 = *a4;
      v12 = EventW;
      if ( *a4 )
      {
        v13 = v24;
        while ( 1 )
        {
          Overlapped.hEvent = v12;
          v14 = v13 % g_dwPageSize;
          v19 = v13 % g_dwPageSize;
          Overlapped.Pointer = (PVOID)(v13 - v14);
          Overlapped.Internal = 0;
          Overlapped.InternalHigh = 0;
          v20 = v14;
          NumberOfBytesRead = 0;
          if ( !ReadFile(v8, v9, g_dwPageSize, &NumberOfBytesRead, &Overlapped) )
          {
            LastError = GetLastError();
            if ( LastError != 38
              && (LastError != 997
               || !GetOverlappedResult(v8, &Overlapped, &NumberOfBytesRead, 1) && GetLastError() != 38) )
            {
              break;
            }
          }
          if ( NumberOfBytesRead <= (unsigned int)v19 )
            goto LABEL_23;
          v16 = NumberOfBytesRead - v19;
          NumberOfBytesRead = v16;
          if ( v16 + v6 > v11 )
          {
            v16 = v11 - v6;
            NumberOfBytesRead = v11 - v6;
          }
          memcpy_0(&a5[v6], &ChunkBuffer[v20], v16);
          v6 += v16;
          v13 = v16 + v24;
          v24 = v13;
          if ( v6 >= v11 )
            goto LABEL_23;
          v9 = ChunkBuffer;
          v8 = v23;
        }
        v17 = GetLastError();
        v5 = (unsigned __int16)v17 | 0x80070000;
        if ( v17 <= 0 )
          v5 = v17;
      }
LABEL_23:
      if ( v12 )
        CloseHandle(v12);
    }
    else
    {
      v5 = -2147024882;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  *a4 = v6;
  return v5;
}

```

## disassembly

```asm
0x18005a9f0  mov     [rsp-40h+arg_10], r8
0x18005a9f5  mov     [rsp-40h+arg_8], rdx
0x18005a9fa  push    rbp
0x18005a9fb  push    rbx
0x18005a9fc  push    rsi
0x18005a9fd  push    rdi
0x18005a9fe  push    r12
0x18005aa00  push    r13
0x18005aa02  push    r14
0x18005aa04  push    r15
0x18005aa06  mov     rbp, rsp
0x18005aa09  sub     rsp, 68h
0x18005aa0d  xor     esi, esi
0x18005aa0f  xor     r14d, r14d
0x18005aa12  mov     r15, r9
0x18005aa15  mov     rdi, rdx
0x18005aa18  test    rcx, rcx
0x18005aa1b  jz      loc_18005ABAC
0x18005aa21  cmp     dword ptr [rcx+10h], 30453034h
0x18005aa28  jnz     loc_18005ABAC
0x18005aa2e  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18005aa32  jz      loc_18005ABAC
0x18005aa38  cmp     [rbp+arg_20], rsi
0x18005aa3c  jz      loc_18005ABAC
0x18005aa42  test    r9, r9
0x18005aa45  jz      loc_18005ABAC
0x18005aa4b  cmp     [r9], esi
0x18005aa4e  jz      loc_18005ABAC
0x18005aa54  call    ?GetReadChunkBuffer@W3_MGD_HANDLER@@QEAAPEAEXZ; W3_MGD_HANDLER::GetReadChunkBuffer(void)
0x18005aa59  mov     [rbp+arg_18], rax
0x18005aa5d  mov     rbx, rax
0x18005aa60  test    rax, rax
0x18005aa63  jnz     short loc_18005AA6F
0x18005aa65  mov     esi, 8007000Eh
0x18005aa6a  jmp     loc_18005ABB1
0x18005aa6f  xor     r9d, r9d; lpName
0x18005aa72  xor     r8d, r8d; bInitialState
0x18005aa75  xor     edx, edx; bManualReset
0x18005aa77  xor     ecx, ecx; lpEventAttributes
0x18005aa79  call    cs:__imp_CreateEventW
0x18005aa7f  mov     r12d, [r15]
0x18005aa82  mov     r13, rax
0x18005aa85  test    r12d, r12d
0x18005aa88  jz      loc_18005AB9C
0x18005aa8e  mov     r9, [rbp+arg_10]
0x18005aa92  mov     r8d, cs:?g_dwPageSize@@3KA; nNumberOfBytesToRead
0x18005aa99  xor     edx, edx
0x18005aa9b  mov     rax, r9
0x18005aa9e  mov     [rbp+Overlapped.hEvent], r13
0x18005aaa2  div     r8
0x18005aaa5  mov     eax, r9d
0x18005aaa8  mov     rcx, rdx
0x18005aaab  mov     [rbp+var_38], rdx
0x18005aaaf  sub     eax, ecx
0x18005aab1  xor     edx, edx
0x18005aab3  mov     dword ptr [rbp+Overlapped.10h], eax
0x18005aab6  mov     rax, r9
0x18005aab9  mov     ecx, ecx
0x18005aabb  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005aabf  sub     rax, rcx
0x18005aac2  mov     [rbp+Overlapped.Internal], rdx
0x18005aac6  shr     rax, 20h
0x18005aaca  mov     dword ptr [rbp+Overlapped.10h+4], eax
0x18005aacd  lea     rax, [rbp+Overlapped]
0x18005aad1  mov     [rbp+Overlapped.InternalHigh], rdx
0x18005aad5  mov     [rbp+var_30], rcx
0x18005aad9  mov     rcx, rdi; hFile
0x18005aadc  mov     [rbp+NumberOfBytesRead], edx
0x18005aadf  mov     rdx, rbx; lpBuffer
0x18005aae2  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18005aae7  call    cs:__imp_ReadFile
0x18005aaed  test    eax, eax
0x18005aaef  jnz     short loc_18005AB2D
0x18005aaf1  call    cs:__imp_GetLastError
0x18005aaf7  cmp     eax, 26h ; '&'
0x18005aafa  jz      short loc_18005AB2D
0x18005aafc  cmp     eax, 3E5h
0x18005ab01  jnz     loc_18005AB88
0x18005ab07  mov     r9d, 1; bWait
0x18005ab0d  lea     r8, [rbp+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x18005ab11  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18005ab15  mov     rcx, rdi; hFile
0x18005ab18  call    cs:__imp_GetOverlappedResult
0x18005ab1e  test    eax, eax
0x18005ab20  jnz     short loc_18005AB2D
0x18005ab22  call    cs:__imp_GetLastError
0x18005ab28  cmp     eax, 26h ; '&'
0x18005ab2b  jnz     short loc_18005AB88
0x18005ab2d  mov     rax, [rbp+var_38]
0x18005ab31  mov     edi, [rbp+NumberOfBytesRead]
0x18005ab34  cmp     edi, eax
0x18005ab36  jbe     short loc_18005AB9C
0x18005ab38  sub     edi, eax
0x18005ab3a  mov     [rbp+NumberOfBytesRead], edi
0x18005ab3d  lea     eax, [rdi+r14]
0x18005ab41  cmp     eax, r12d
0x18005ab44  jbe     short loc_18005AB4F
0x18005ab46  mov     edi, r12d
0x18005ab49  sub     edi, r14d
0x18005ab4c  mov     [rbp+NumberOfBytesRead], edi
0x18005ab4f  mov     rdx, [rbp+var_30]
0x18005ab53  add     rdx, [rbp+arg_18]; Src
0x18005ab57  mov     ecx, r14d
0x18005ab5a  add     rcx, [rbp+arg_20]; void *
0x18005ab5e  mov     r8d, edi; Size
0x18005ab61  mov     ebx, edi
0x18005ab63  call    memcpy_0
0x18005ab68  mov     r9, [rbp+arg_10]
0x18005ab6c  add     r14d, edi
0x18005ab6f  add     r9, rbx
0x18005ab72  mov     [rbp+arg_10], r9
0x18005ab76  cmp     r14d, r12d
0x18005ab79  jnb     short loc_18005AB9C
0x18005ab7b  mov     rbx, [rbp+arg_18]
0x18005ab7f  mov     rdi, [rbp+arg_8]
0x18005ab83  jmp     loc_18005AA92
0x18005ab88  call    cs:__imp_GetLastError
0x18005ab8e  movzx   esi, ax
0x18005ab91  or      esi, 80070000h
0x18005ab97  test    eax, eax
0x18005ab99  cmovle  esi, eax
0x18005ab9c  test    r13, r13
0x18005ab9f  jz      short loc_18005ABB1
0x18005aba1  mov     rcx, r13; hObject
0x18005aba4  call    cs:__imp_CloseHandle
0x18005abaa  jmp     short loc_18005ABB1
0x18005abac  mov     esi, 80070057h
0x18005abb1  mov     [r15], r14d
0x18005abb4  mov     eax, esi
0x18005abb6  add     rsp, 68h
0x18005abba  pop     r15
0x18005abbc  pop     r14
0x18005abbe  pop     r13
0x18005abc0  pop     r12
0x18005abc2  pop     rdi
0x18005abc3  pop     rsi
0x18005abc4  pop     rbx
0x18005abc5  pop     rbp
0x18005abc6  retn
```
