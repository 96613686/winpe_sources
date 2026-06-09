# WimSerializeXml

- ea: `0x180015ae4`
- end: `0x180015d69`
- name: `WimSerializeXml`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180013878`

## callees

- `0x180011bb8`
- `0x180014778`
- `0x180015ae4`
- `0x18003f578`
- `0x180040ef8`
- `0x180044c00`
- `0x180044e48`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180015caa`
- `KERNEL32!WriteFile` at `0x180015caa`
- `KERNEL32!HeapFree` at `0x180015bfa`
- `KERNEL32!HeapFree` at `0x180015d22`
- `KERNEL32!HeapFree` at `0x180015bfa`
- `KERNEL32!HeapFree` at `0x180015d22`
- `KERNEL32!GetLastError` at `0x180015b6b`
- `KERNEL32!GetLastError` at `0x180015b86`
- `KERNEL32!GetLastError` at `0x180015ccd`
- `KERNEL32!GetLastError` at `0x180015cec`
- `KERNEL32!GetLastError` at `0x180015b6b`
- `KERNEL32!GetLastError` at `0x180015b86`
- `KERNEL32!GetLastError` at `0x180015ccd`
- `KERNEL32!GetLastError` at `0x180015cec`
- `KERNEL32!SetLastError` at `0x180015d43`
- `KERNEL32!SetLastError` at `0x180015d43`
- `KERNEL32!GetFileSizeEx` at `0x180015b5b`
- `KERNEL32!GetFileSizeEx` at `0x180015b5b`
- `KERNEL32!GetProcessHeap` at `0x180015be6`
- `KERNEL32!GetProcessHeap` at `0x180015d0e`
- `KERNEL32!GetProcessHeap` at `0x180015be6`
- `KERNEL32!GetProcessHeap` at `0x180015d0e`

## pseudocode

```c
_BOOL8 WimSerializeXml(Unattend **a1, void *a2, __int64 a3, ...)
{
  _WORD *v5; // rdi
  __int64 v6; // rsi
  void *WimFileHandle; // rax
  signed int LastError; // eax
  signed int v9; // ecx
  signed int v10; // eax
  signed int RootNode; // ebx
  int v12; // eax
  void *v13; // r14
  HANDLE ProcessHeap; // rax
  Unattend *v15; // r14
  signed int v16; // eax
  unsigned __int64 v17; // rax
  unsigned int v18; // esi
  signed int v19; // eax
  signed int v20; // ecx
  signed int v21; // eax
  HANDLE v22; // rax
  __int64 v24; // [rsp+30h] [rbp-20h] BYREF
  __int128 v25; // [rsp+40h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp+40h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+A8h] [rbp+58h] BYREF
  va_list FileSizea; // [rsp+A8h] [rbp+58h]
  _WORD *v29; // [rsp+B0h] [rbp+60h] BYREF
  va_list va1; // [rsp+B0h] [rbp+60h]
  va_list va2; // [rsp+B8h] [rbp+68h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(FileSizea, a3);
  FileSize.QuadPart = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  va_arg(va2, _QWORD);
  v29 = 0;
  v24 = 0;
  v5 = 0;
  if ( a1 )
  {
    v6 = -1;
    if ( a2 != (void *)-1LL )
    {
      if ( !a3 || (*(_BYTE *)(a3 + 64) & 8) != 0 )
      {
        RootNode = 0;
      }
      else
      {
        WimFileHandle = (void *)GetWimFileHandle(a3);
        FileSize.QuadPart = 0;
        lpMem = 0;
        if ( !GetFileSizeEx(WimFileHandle, (PLARGE_INTEGER)FileSizea) )
        {
          LastError = GetLastError();
          v9 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v9 = LastError;
          if ( v9 >= 0 )
          {
            RootNode = -2147467259;
          }
          else
          {
            v10 = GetLastError();
            RootNode = (unsigned __int16)v10 | 0x80070000;
            if ( v10 <= 0 )
              RootNode = v10;
          }
          if ( RootNode < 0 )
            goto LABEL_41;
        }
        v12 = StrAllocatingPrintf(&lpMem, L"%I64u", FileSize.QuadPart);
        v13 = lpMem;
        RootNode = v12;
        if ( v12 >= 0 )
          RootNode = UnattendCtxSetString((_DWORD)a1, (unsigned int)L"WIM\\TOTALBYTES", 0, (_DWORD)lpMem);
        if ( v13 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v13);
        }
      }
      if ( RootNode >= 0 )
      {
        v15 = *a1;
        if ( *a1 )
        {
          RootNode = Unattend::GetRootNode(*a1, (struct UnattendNode *)&v25);
          if ( RootNode >= 0 )
          {
            v16 = Unattend::SerializeToBuffer(v15, &v25, (_WORD **)va1, &v24, 0);
            v5 = v29;
            RootNode = v16;
          }
        }
        else
        {
          RootNode = -2147024809;
        }
        if ( RootNode >= 0 )
        {
          do
            ++v6;
          while ( v5[v6] );
          v17 = 2 * v6 + 2;
          v18 = -1;
          if ( v17 <= 0xFFFFFFFF )
            v18 = v17;
          RootNode = v17 > 0xFFFFFFFF ? 0x80070216 : 0;
          if ( v17 <= 0xFFFFFFFF )
          {
            FileSize.LowPart = 0;
            if ( WriteFile(a2, v5, v18 - 2, (LPDWORD)FileSizea, 0) && FileSize.LowPart == v18 - 2LL )
            {
              RootNode = 0;
            }
            else
            {
              v19 = GetLastError();
              v20 = (unsigned __int16)v19 | 0x80070000;
              if ( v19 <= 0 )
                v20 = v19;
              if ( v20 >= 0 )
              {
                RootNode = -2147467259;
              }
              else
              {
                v21 = GetLastError();
                RootNode = (unsigned __int16)v21 | 0x80070000;
                if ( v21 <= 0 )
                  RootNode = v21;
              }
            }
          }
        }
        if ( v5 )
        {
          v22 = GetProcessHeap();
          HeapFree(v22, 0, v5);
        }
      }
LABEL_41:
      SetLastErrorFromHresult(RootNode);
      return RootNode >= 0;
    }
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180015ae4  mov     [rsp-38h+arg_8], rbx
0x180015ae9  mov     qword ptr [rsp-38h+FileSize], r9
0x180015aee  push    rbp
0x180015aef  push    rsi
0x180015af0  push    rdi
0x180015af1  push    r12
0x180015af3  push    r13
0x180015af5  push    r14
0x180015af7  push    r15
0x180015af9  mov     rbp, rsp
0x180015afc  sub     rsp, 50h
0x180015b00  xor     r13d, r13d
0x180015b03  mov     r12, rdx
0x180015b06  mov     [rbp+arg_20], r13
0x180015b0a  mov     r15, rcx
0x180015b0d  mov     [rbp+var_20], r13
0x180015b11  mov     edi, r13d
0x180015b14  test    rcx, rcx
0x180015b17  jz      loc_180015D3E
0x180015b1d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180015b21  cmp     rdx, rsi
0x180015b24  jz      loc_180015D3E
0x180015b2a  mov     r14d, 80070000h
0x180015b30  test    r8, r8
0x180015b33  jz      loc_180015C08
0x180015b39  test    byte ptr [r8+40h], 8
0x180015b3e  jnz     loc_180015C08
0x180015b44  mov     rcx, r8
0x180015b47  call    GetWimFileHandle
0x180015b4c  mov     rcx, rax; hFile
0x180015b4f  mov     qword ptr [rbp+FileSize], r13
0x180015b53  lea     rdx, [rbp+FileSize]; lpFileSize
0x180015b57  mov     [rbp+lpMem], r13
0x180015b5b  call    cs:__imp_GetFileSizeEx
0x180015b62  nop     dword ptr [rax+rax+00h]
0x180015b67  test    eax, eax
0x180015b69  jnz     short loc_180015BAC
0x180015b6b  call    cs:__imp_GetLastError
0x180015b72  nop     dword ptr [rax+rax+00h]
0x180015b77  movzx   ecx, ax
0x180015b7a  or      ecx, r14d
0x180015b7d  test    eax, eax
0x180015b7f  cmovle  ecx, eax
0x180015b82  test    ecx, ecx
0x180015b84  jns     short loc_180015B9F
0x180015b86  call    cs:__imp_GetLastError
0x180015b8d  nop     dword ptr [rax+rax+00h]
0x180015b92  movzx   ebx, ax
0x180015b95  or      ebx, r14d
0x180015b98  test    eax, eax
0x180015b9a  cmovle  ebx, eax
0x180015b9d  jmp     short loc_180015BA4
0x180015b9f  mov     ebx, 80004005h
0x180015ba4  test    ebx, ebx
0x180015ba6  js      loc_180015D2E
0x180015bac  mov     r8, qword ptr [rbp+FileSize]
0x180015bb0  lea     rdx, aI64u_0; "%I64u"
0x180015bb7  lea     rcx, [rbp+lpMem]
0x180015bbb  call    StrAllocatingPrintf
0x180015bc0  mov     r14, [rbp+lpMem]
0x180015bc4  mov     ebx, eax
0x180015bc6  test    eax, eax
0x180015bc8  js      short loc_180015BE1
0x180015bca  mov     r9, r14
0x180015bcd  lea     rdx, aWimTotalbytes; "WIM\\TOTALBYTES"
0x180015bd4  xor     r8d, r8d
0x180015bd7  mov     rcx, r15
0x180015bda  call    UnattendCtxSetString
0x180015bdf  mov     ebx, eax
0x180015be1  test    r14, r14
0x180015be4  jz      short loc_180015C0B
0x180015be6  call    cs:__imp_GetProcessHeap
0x180015bed  nop     dword ptr [rax+rax+00h]
0x180015bf2  mov     r8, r14; lpMem
0x180015bf5  xor     edx, edx; dwFlags
0x180015bf7  mov     rcx, rax; hHeap
0x180015bfa  call    cs:__imp_HeapFree
0x180015c01  nop     dword ptr [rax+rax+00h]
0x180015c06  jmp     short loc_180015C0B
0x180015c08  mov     ebx, r13d
0x180015c0b  test    ebx, ebx
0x180015c0d  js      loc_180015D2E
0x180015c13  mov     r14, [r15]
0x180015c16  test    r14, r14
0x180015c19  jz      short loc_180015C57
0x180015c1b  lea     rdx, [rbp+var_10]; struct UnattendNode *
0x180015c1f  mov     rcx, r14; this
0x180015c22  call    ?GetRootNode@Unattend@@QEAAJAEAVUnattendNode@@@Z; Unattend::GetRootNode(UnattendNode &)
0x180015c27  mov     ebx, eax
0x180015c29  test    eax, eax
0x180015c2b  js      short loc_180015C5C
0x180015c2d  movaps  xmm0, [rbp+var_10]
0x180015c31  lea     r9, [rbp+var_20]
0x180015c35  lea     r8, [rbp+arg_20]
0x180015c39  movdqa  [rbp+var_10], xmm0
0x180015c3e  lea     rdx, [rbp+var_10]
0x180015c42  mov     dword ptr [rsp+50h+lpOverlapped], r13d
0x180015c47  mov     rcx, r14
0x180015c4a  call    ?SerializeToBuffer@Unattend@@QEAAJVUnattendNode@@PEAPEAGPEA_KH@Z; Unattend::SerializeToBuffer(UnattendNode,ushort * *,unsigned __int64 *,int)
0x180015c4f  mov     rdi, [rbp+arg_20]
0x180015c53  mov     ebx, eax
0x180015c55  jmp     short loc_180015C5C
0x180015c57  mov     ebx, 80070057h
0x180015c5c  test    ebx, ebx
0x180015c5e  js      loc_180015D09
0x180015c64  inc     rsi
0x180015c67  cmp     [rdi+rsi*2], r13w
0x180015c6c  jnz     short loc_180015C64
0x180015c6e  lea     rax, ds:2[rsi*2]
0x180015c76  mov     ecx, 0FFFFFFFFh
0x180015c7b  cmp     rax, rcx
0x180015c7e  mov     esi, ecx
0x180015c80  cmovbe  esi, eax
0x180015c83  cmp     rcx, rax
0x180015c86  sbb     ebx, ebx
0x180015c88  and     ebx, 80070216h
0x180015c8e  cmp     rax, rcx
0x180015c91  ja      short loc_180015D09
0x180015c93  lea     r8d, [rsi-2]; nNumberOfBytesToWrite
0x180015c97  mov     dword ptr [rbp+FileSize], r13d
0x180015c9b  lea     r9, [rbp+FileSize]; lpNumberOfBytesWritten
0x180015c9f  mov     [rsp+50h+lpOverlapped], r13; lpOverlapped
0x180015ca4  mov     rdx, rdi; lpBuffer
0x180015ca7  mov     rcx, r12; hFile
0x180015caa  call    cs:__imp_WriteFile
0x180015cb1  nop     dword ptr [rax+rax+00h]
0x180015cb6  test    eax, eax
0x180015cb8  jz      short loc_180015CCD
0x180015cba  mov     eax, dword ptr [rbp+FileSize]
0x180015cbd  mov     ecx, esi
0x180015cbf  sub     rcx, 2
0x180015cc3  cmp     rax, rcx
0x180015cc6  jnz     short loc_180015CCD
0x180015cc8  mov     ebx, r13d
0x180015ccb  jmp     short loc_180015D09
0x180015ccd  call    cs:__imp_GetLastError
0x180015cd4  nop     dword ptr [rax+rax+00h]
0x180015cd9  movzx   ecx, ax
0x180015cdc  mov     esi, 80070000h
0x180015ce1  or      ecx, esi
0x180015ce3  test    eax, eax
0x180015ce5  cmovle  ecx, eax
0x180015ce8  test    ecx, ecx
0x180015cea  jns     short loc_180015D04
0x180015cec  call    cs:__imp_GetLastError
0x180015cf3  nop     dword ptr [rax+rax+00h]
0x180015cf8  movzx   ebx, ax
0x180015cfb  or      ebx, esi
0x180015cfd  test    eax, eax
0x180015cff  cmovle  ebx, eax
0x180015d02  jmp     short loc_180015D09
0x180015d04  mov     ebx, 80004005h
0x180015d09  test    rdi, rdi
0x180015d0c  jz      short loc_180015D2E
0x180015d0e  call    cs:__imp_GetProcessHeap
0x180015d15  nop     dword ptr [rax+rax+00h]
0x180015d1a  mov     r8, rdi; lpMem
0x180015d1d  xor     edx, edx; dwFlags
0x180015d1f  mov     rcx, rax; hHeap
0x180015d22  call    cs:__imp_HeapFree
0x180015d29  nop     dword ptr [rax+rax+00h]
0x180015d2e  mov     ecx, ebx; dwErrCode
0x180015d30  call    SetLastErrorFromHresult
0x180015d35  not     ebx
0x180015d37  shr     ebx, 1Fh
0x180015d3a  mov     eax, ebx
0x180015d3c  jmp     short loc_180015D51
0x180015d3e  mov     ecx, 57h ; 'W'; dwErrCode
0x180015d43  call    cs:__imp_SetLastError
0x180015d4a  nop     dword ptr [rax+rax+00h]
0x180015d4f  xor     eax, eax
0x180015d51  mov     rbx, [rsp+50h+arg_8]
0x180015d59  add     rsp, 50h
0x180015d5d  pop     r15
0x180015d5f  pop     r14
0x180015d61  pop     r13
0x180015d63  pop     r12
0x180015d65  pop     rdi
0x180015d66  pop     rsi
0x180015d67  pop     rbp
0x180015d68  retn
```
