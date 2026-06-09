# IsDuplicateManifestFileEntry(void * const,char * const)

- ea: `0x1800105c0`
- end: `0x180010761`
- name: `?IsDuplicateManifestFileEntry@@YAHQEAXQEAD@Z`
- size: `417`
- prototype: `__int64 __fastcall(HANDLE hFile, char *const)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000fa80`
- `0x18000fba4`
- `0x18000fd80`
- `0x18000ff64`
- `0x180010130`
- `0x1800102e0`
- `0x180010400`

## callees

- `0x180003b90`
- `0x180007820`
- `0x1800105c0`

## import_xrefs

- `msvcrt!tolower` at `0x1800106bb`
- `msvcrt!tolower` at `0x1800106c5`
- `msvcrt!tolower` at `0x1800106bb`
- `msvcrt!tolower` at `0x1800106c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010662`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180010691`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180010691`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180010637`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001065a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180010719`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180010637`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001065a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180010719`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800105e4`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800105e4`

## pseudocode

```c
__int64 __fastcall IsDuplicateManifestFileEntry(HANDLE hFile, char *const a2)
{
  char *v2; // rdi
  unsigned int v3; // r12d
  unsigned int LastErrorHRESULT; // eax
  DWORD v6; // ebx
  _BYTE *v7; // rax
  _BYTE *v8; // r13
  _BYTE *i; // rsi
  _BYTE *v10; // rbp
  char *v11; // r14
  int v12; // ebx
  int v13; // edi
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+18h] BYREF
  DWORD v17; // [rsp+88h] [rbp+20h]

  v2 = a2;
  v3 = 0;
  if ( !FlushFileBuffers(hFile)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      LastErrorHRESULT);
  }
  v6 = SetFilePointer(hFile, 0, 0, 1u);
  v17 = v6;
  if ( v6 != -1 )
  {
    SetFilePointer(hFile, 0, 0, 0);
    v7 = CoTaskMemAlloc(v6);
    v8 = v7;
    if ( v7 )
    {
      NumberOfBytesRead = 0;
      if ( ReadFile(hFile, v7, v6, &NumberOfBytesRead, 0) )
      {
        if ( *v2 )
        {
          for ( i = v8; *i; ++i )
          {
            v10 = i;
            v11 = v2;
            do
            {
              if ( !*v11 )
                break;
              v12 = (char)*v10;
              v13 = tolower(*v11);
              if ( tolower(v12) != v13 )
                break;
              ++v10;
              ++v11;
            }
            while ( *v10 );
            if ( !*v11 )
            {
              if ( !i )
                break;
              goto LABEL_18;
            }
            v2 = a2;
          }
        }
        else
        {
LABEL_18:
          v3 = 1;
        }
      }
      CoTaskMemFree(v8);
      v6 = v17;
    }
    SetFilePointer(hFile, v6, 0, 0);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800105c0  mov     [rsp+arg_0], rbx
0x1800105c5  mov     [rsp+arg_8], rdx
0x1800105ca  push    rbp
0x1800105cb  push    rsi
0x1800105cc  push    rdi
0x1800105cd  push    r12
0x1800105cf  push    r13
0x1800105d1  push    r14
0x1800105d3  push    r15
0x1800105d5  sub     rsp, 30h
0x1800105d9  xor     ebp, ebp
0x1800105db  mov     rdi, rdx
0x1800105de  mov     r12d, ebp
0x1800105e1  mov     r15, rcx
0x1800105e4  call    cs:__imp_FlushFileBuffers
0x1800105ea  lea     rsi, WPP_GLOBAL_Control
0x1800105f1  test    eax, eax
0x1800105f3  jnz     short loc_180010629
0x1800105f5  mov     rax, cs:WPP_GLOBAL_Control
0x1800105fc  cmp     rax, rsi
0x1800105ff  jz      short loc_180010629
0x180010601  test    byte ptr [rax+1Ch], 4
0x180010605  jz      short loc_180010629
0x180010607  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001060c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010613  lea     edx, [rbp+13h]
0x180010616  mov     r9d, eax
0x180010619  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x180010620  mov     rcx, [rcx+10h]
0x180010624  call    WPP_SF_D
0x180010629  mov     r9d, 1; dwMoveMethod
0x18001062f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180010632  xor     edx, edx; lDistanceToMove
0x180010634  mov     rcx, r15; hFile
0x180010637  call    cs:__imp_SetFilePointer
0x18001063d  mov     ebx, eax
0x18001063f  mov     [rsp+68h+arg_18], ebx
0x180010646  cmp     eax, 0FFFFFFFFh
0x180010649  jz      loc_18001071F
0x18001064f  xor     r9d, r9d; dwMoveMethod
0x180010652  xor     r8d, r8d; lpDistanceToMoveHigh
0x180010655  xor     edx, edx; lDistanceToMove
0x180010657  mov     rcx, r15; hFile
0x18001065a  call    cs:__imp_SetFilePointer
0x180010660  mov     ecx, ebx; cb
0x180010662  call    cs:__imp_CoTaskMemAlloc
0x180010668  mov     r13, rax
0x18001066b  test    rax, rax
0x18001066e  jz      loc_18001070E
0x180010674  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001067c  mov     [rsp+68h+NumberOfBytesRead], ebp
0x180010683  mov     r8d, ebx; nNumberOfBytesToRead
0x180010686  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x18001068b  mov     rdx, rax; lpBuffer
0x18001068e  mov     rcx, r15; hFile
0x180010691  call    cs:__imp_ReadFile
0x180010697  test    eax, eax
0x180010699  jz      short loc_1800106F7
0x18001069b  cmp     [rdi], bpl
0x18001069e  jz      short loc_1800106F1
0x1800106a0  mov     rsi, r13
0x1800106a3  cmp     [rsi], bpl
0x1800106a6  jz      short loc_1800106F7
0x1800106a8  mov     rbp, rsi
0x1800106ab  mov     r14, rdi
0x1800106ae  cmp     [r14], r12b
0x1800106b1  jz      short loc_1800106DB
0x1800106b3  movsx   ecx, byte ptr [r14]; C
0x1800106b7  movsx   ebx, byte ptr [rbp+0]
0x1800106bb  call    cs:__imp_tolower
0x1800106c1  mov     ecx, ebx; C
0x1800106c3  mov     edi, eax
0x1800106c5  call    cs:__imp_tolower
0x1800106cb  cmp     eax, edi
0x1800106cd  jnz     short loc_1800106DB
0x1800106cf  inc     rbp
0x1800106d2  inc     r14
0x1800106d5  cmp     [rbp+0], r12b
0x1800106d9  jnz     short loc_1800106AE
0x1800106db  xor     ebp, ebp
0x1800106dd  cmp     [r14], bpl
0x1800106e0  jz      short loc_1800106EC
0x1800106e2  mov     rdi, [rsp+68h+arg_8]
0x1800106e7  inc     rsi
0x1800106ea  jmp     short loc_1800106A3
0x1800106ec  test    rsi, rsi
0x1800106ef  jz      short loc_1800106F7
0x1800106f1  mov     r12d, 1
0x1800106f7  mov     rcx, r13; pv
0x1800106fa  call    cs:__imp_CoTaskMemFree
0x180010700  mov     ebx, [rsp+68h+arg_18]
0x180010707  lea     rsi, WPP_GLOBAL_Control
0x18001070e  xor     r9d, r9d; dwMoveMethod
0x180010711  xor     r8d, r8d; lpDistanceToMoveHigh
0x180010714  mov     edx, ebx; lDistanceToMove
0x180010716  mov     rcx, r15; hFile
0x180010719  call    cs:__imp_SetFilePointer
0x18001071f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010726  cmp     rcx, rsi
0x180010729  jz      short loc_180010749
0x18001072b  test    byte ptr [rcx+1Ch], 10h
0x18001072f  jz      short loc_180010749
0x180010731  mov     rcx, [rcx+10h]
0x180010735  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18001073c  mov     edx, 14h
0x180010741  mov     r9d, r12d
0x180010744  call    WPP_SF_D
0x180010749  mov     rbx, [rsp+68h+arg_0]
0x18001074e  mov     eax, r12d
0x180010751  add     rsp, 30h
0x180010755  pop     r15
0x180010757  pop     r14
0x180010759  pop     r13
0x18001075b  pop     r12
0x18001075d  pop     rdi
0x18001075e  pop     rsi
0x18001075f  pop     rbp
0x180010760  retn
```
