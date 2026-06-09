# WsUpdateRegistryToMatchWksta

- ea: `0x18002d1e8`
- end: `0x18002d4ef`
- name: `WsUpdateRegistryToMatchWksta`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18002ce00`

## callees

- `0x180007958`
- `0x180007a90`
- `0x18002d1e8`
- `0x18003169c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d2c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d31e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d2c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d31e`

## string_xrefs

- `0x18002d359`: `MaxThreads`
- `0x18002d38f`: `CacheFileTimeout`
- `0x18002d448`: `UseLockReadUnlock`
- `0x18002d430`: `UseRawRead`
- `0x18002d424`: `UseRawWrite`
- `0x18002d46c`: `UseWriteRawData`
- `0x18002d4bd`: `BufFilesDenyWrite`
- `0x18002d4b4`: `BufReadOnlyFiles`
- `0x18002d4ab`: `ForceCoreCreateMode`
- `0x18002d496`: `ReadAheadThroughput`

## pseudocode

```c
LSTATUS __fastcall WsUpdateRegistryToMatchWksta(unsigned int a1, _DWORD *a2, __int64 a3)
{
  LSTATUS result; // eax
  HKEY *v6; // rdi
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  const WCHAR *v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rsi
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  const wchar_t *v22; // rdx
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  unsigned int v25; // ebx
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  unsigned int v29; // ebx
  unsigned int v30; // ebx
  unsigned int v31; // ebx
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  HKEY *Data; // [rsp+70h] [rbp+38h] BYREF

  Data = 0;
  result = NetpOpenConfigDataEx(&Data, a2, a3, 0);
  if ( !result )
  {
    v6 = Data;
    if ( a1 > 0x418 )
    {
      result = 1056;
      if ( a1 > 0x420 )
      {
        v29 = a1 - 1057;
        if ( v29 )
        {
          v30 = v29 - 1;
          if ( v30 )
          {
            v31 = v30 - 1;
            if ( v31 )
            {
              v32 = v31 - 1;
              if ( v32 )
              {
                v33 = v32 - 1;
                if ( v33 )
                {
                  if ( v33 == 1 )
                  {
                    v13 = L"ReadAheadThroughput";
                    goto LABEL_19;
                  }
                  goto LABEL_72;
                }
                v22 = L"Use512ByteMaxTransfer";
              }
              else
              {
                v22 = L"ForceCoreCreateMode";
              }
            }
            else
            {
              v22 = L"BufReadOnlyFiles";
            }
          }
          else
          {
            v22 = L"BufFilesDenyWrite";
          }
        }
        else
        {
          v22 = L"UseEncryption";
        }
      }
      else if ( a1 == 1056 )
      {
        v22 = L"UseWriteRawData";
      }
      else
      {
        v23 = a1 - 1049;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            v25 = v24 - 1;
            if ( v25 )
            {
              v26 = v25 - 1;
              if ( v26 )
              {
                v27 = v26 - 1;
                if ( v27 )
                {
                  v28 = v27 - 1;
                  if ( v28 )
                  {
                    if ( v28 != 1 )
                      goto LABEL_72;
                    v22 = L"UseRawWrite";
                  }
                  else
                  {
                    v22 = L"UseRawRead";
                  }
                }
                else
                {
                  v22 = L"UtilizeNtCaching";
                }
              }
              else
              {
                v22 = L"UseLockReadUnlock";
              }
            }
            else
            {
              v22 = L"BufNamedPipes";
            }
          }
          else
          {
            v22 = L"UseCloseBehind";
          }
        }
        else
        {
          v22 = L"UseUnlockBehind";
        }
      }
    }
    else
    {
      if ( a1 != 1048 )
      {
        result = 1033;
        if ( a1 <= 0x409 )
        {
          if ( a1 == 1033 )
          {
            v13 = L"MaxThreads";
          }
          else
          {
            v7 = a1 - 502;
            if ( !v7 )
            {
              v14 = qword_180052010;
              v15 = 0;
              if ( *(_QWORD *)qword_180052010 )
              {
                do
                {
                  if ( *(_DWORD *)(v14 + 40 * v15 + 28) == 1 )
                  {
                    LODWORD(Data) = **(_DWORD **)(v14 + 40 * v15 + 8);
                    result = RegSetValueExW(*v6, *(LPCWSTR *)(v14 + 40 * v15), 0, 4u, (const BYTE *)&Data, 4u);
                  }
                  else
                  {
                    result = WsSetConfigBool(v6, *(_QWORD *)(v14 + 40 * v15), **(unsigned int **)(v14 + 40 * v15 + 8));
                  }
                  v14 = qword_180052010;
                  v15 = (unsigned int)(v15 + 1);
                }
                while ( *(_QWORD *)(qword_180052010 + 40 * v15) );
              }
              goto LABEL_72;
            }
            v8 = v7 - 508;
            if ( v8 )
            {
              v9 = v8 - 1;
              if ( v9 )
              {
                v10 = v9 - 1;
                if ( v10 )
                {
                  v11 = v10 - 1;
                  if ( v11 )
                  {
                    v12 = v11 - 5;
                    if ( v12 )
                    {
                      if ( v12 != 5 )
                        goto LABEL_72;
                      v13 = L"SizCharBuf";
                    }
                    else
                    {
                      v13 = L"SessTimeout";
                    }
                  }
                  else
                  {
                    v13 = L"KeepConn";
                  }
                }
                else
                {
                  v13 = L"MaxCollectionCount";
                }
              }
              else
              {
                v13 = L"CollectionTime";
              }
            }
            else
            {
              v13 = L"CharWait";
            }
          }
          goto LABEL_19;
        }
        v16 = a1 - 1041;
        if ( !v16 )
        {
          v13 = L"LockQuota";
          goto LABEL_19;
        }
        v17 = v16 - 1;
        if ( !v17 )
        {
          v13 = L"LockIncrement";
          goto LABEL_19;
        }
        v18 = v17 - 1;
        if ( !v18 )
        {
          v13 = L"LockMaximum";
          goto LABEL_19;
        }
        v19 = v18 - 1;
        if ( !v19 )
        {
          v13 = L"PipeIncrement";
          goto LABEL_19;
        }
        v20 = v19 - 1;
        if ( !v20 )
        {
          v13 = L"PipeMaximum";
          goto LABEL_19;
        }
        v21 = v20 - 1;
        if ( !v21 )
        {
          v13 = L"DormantFileLimit";
          goto LABEL_19;
        }
        if ( v21 == 1 )
        {
          v13 = L"CacheFileTimeout";
LABEL_19:
          LODWORD(Data) = *a2;
          result = RegSetValueExW(*v6, v13, 0, 4u, (const BYTE *)&Data, 4u);
        }
LABEL_72:
        if ( v6 )
          return NetpCloseConfigData(v6);
        return result;
      }
      v22 = L"UseOpportunisticLocking";
    }
    result = WsSetConfigBool(Data, v22, (unsigned int)*a2);
    goto LABEL_72;
  }
  return result;
}

```

## disassembly

```asm
0x18002d1e8  mov     [rsp-20h+Data], r8
0x18002d1ed  push    rbp
0x18002d1ee  push    rbx
0x18002d1ef  push    rsi
0x18002d1f0  push    rdi
0x18002d1f1  mov     rbp, rsp
0x18002d1f4  sub     rsp, 38h
0x18002d1f8  mov     ebx, ecx
0x18002d1fa  mov     [rbp+Data], 0
0x18002d202  lea     rcx, [rbp+Data]
0x18002d206  xor     r9d, r9d
0x18002d209  mov     rsi, rdx
0x18002d20c  call    NetpOpenConfigDataEx
0x18002d211  test    eax, eax
0x18002d213  jnz     loc_18002D4E5
0x18002d219  mov     rdi, [rbp+Data]
0x18002d21d  mov     eax, 418h
0x18002d222  cmp     ebx, eax
0x18002d224  ja      loc_18002D3EF
0x18002d22a  jz      loc_18002D3E3
0x18002d230  mov     eax, 409h
0x18002d235  cmp     ebx, eax
0x18002d237  ja      loc_18002D365
0x18002d23d  jz      loc_18002D359
0x18002d243  sub     ebx, 1F6h
0x18002d249  jz      loc_18002D2D9
0x18002d24f  sub     ebx, 1FCh
0x18002d255  jz      short loc_18002D2A1
0x18002d257  sub     ebx, 1
0x18002d25a  jz      short loc_18002D298
0x18002d25c  sub     ebx, 1
0x18002d25f  jz      short loc_18002D28F
0x18002d261  sub     ebx, 1
0x18002d264  jz      short loc_18002D286
0x18002d266  sub     ebx, 5
0x18002d269  jz      short loc_18002D27D
0x18002d26b  cmp     ebx, 5
0x18002d26e  jnz     loc_18002D4D8
0x18002d274  lea     rdx, aSizcharbuf; "SizCharBuf"
0x18002d27b  jmp     short loc_18002D2A8
0x18002d27d  lea     rdx, aSesstimeout; "SessTimeout"
0x18002d284  jmp     short loc_18002D2A8
0x18002d286  lea     rdx, aKeepconn; "KeepConn"
0x18002d28d  jmp     short loc_18002D2A8
0x18002d28f  lea     rdx, aMaxcollectionc; "MaxCollectionCount"
0x18002d296  jmp     short loc_18002D2A8
0x18002d298  lea     rdx, aCollectiontime; "CollectionTime"
0x18002d29f  jmp     short loc_18002D2A8
0x18002d2a1  lea     rdx, aCharwait; "CharWait"
0x18002d2a8  mov     eax, [rsi]
0x18002d2aa  mov     ebx, 4
0x18002d2af  mov     dword ptr [rbp+Data], eax
0x18002d2b2  mov     r9d, ebx; dwType
0x18002d2b5  mov     rcx, [rdi]; hKey
0x18002d2b8  lea     rax, [rbp+Data]
0x18002d2bc  mov     [rsp+38h+cbData], ebx; cbData
0x18002d2c0  xor     r8d, r8d; Reserved
0x18002d2c3  mov     [rsp+38h+lpData], rax; lpData
0x18002d2c8  call    cs:__imp_RegSetValueExW
0x18002d2cf  nop     dword ptr [rax+rax+00h]
0x18002d2d4  jmp     loc_18002D4D8
0x18002d2d9  mov     rdx, cs:qword_180052010
0x18002d2e0  xor     esi, esi
0x18002d2e2  cmp     [rdx], rsi
0x18002d2e5  jz      loc_18002D4D8
0x18002d2eb  lea     ebx, [rsi+4]
0x18002d2ee  lea     r10, [rsi+rsi*4]
0x18002d2f2  cmp     dword ptr [rdx+r10*8+1Ch], 1
0x18002d2f8  jnz     short loc_18002D32C
0x18002d2fa  mov     rax, [rdx+r10*8+8]
0x18002d2ff  mov     r9d, ebx; dwType
0x18002d302  mov     [rsp+38h+cbData], ebx; cbData
0x18002d306  xor     r8d, r8d; Reserved
0x18002d309  mov     ecx, [rax]
0x18002d30b  lea     rax, [rbp+Data]
0x18002d30f  mov     dword ptr [rbp+Data], ecx
0x18002d312  mov     rdx, [rdx+r10*8]; lpValueName
0x18002d316  mov     rcx, [rdi]; hKey
0x18002d319  mov     [rsp+38h+lpData], rax; lpData
0x18002d31e  call    cs:__imp_RegSetValueExW
0x18002d325  nop     dword ptr [rax+rax+00h]
0x18002d32a  jmp     short loc_18002D340
0x18002d32c  mov     r8, [rdx+r10*8+8]
0x18002d331  mov     rcx, rdi
0x18002d334  mov     rdx, [rdx+r10*8]
0x18002d338  mov     r8d, [r8]
0x18002d33b  call    WsSetConfigBool
0x18002d340  mov     rdx, cs:qword_180052010
0x18002d347  inc     esi
0x18002d349  lea     rcx, [rsi+rsi*4]
0x18002d34d  cmp     qword ptr [rdx+rcx*8], 0
0x18002d352  jnz     short loc_18002D2EE
0x18002d354  jmp     loc_18002D4D8
0x18002d359  lea     rdx, aMaxthreads; "MaxThreads"
0x18002d360  jmp     loc_18002D2A8
0x18002d365  sub     ebx, 411h
0x18002d36b  jz      short loc_18002D3D7
0x18002d36d  sub     ebx, 1
0x18002d370  jz      short loc_18002D3CB
0x18002d372  sub     ebx, 1
0x18002d375  jz      short loc_18002D3BF
0x18002d377  sub     ebx, 1
0x18002d37a  jz      short loc_18002D3B3
0x18002d37c  sub     ebx, 1
0x18002d37f  jz      short loc_18002D3A7
0x18002d381  sub     ebx, 1
0x18002d384  jz      short loc_18002D39B
0x18002d386  cmp     ebx, 1
0x18002d389  jnz     loc_18002D4D8
0x18002d38f  lea     rdx, aCachefiletimeo; "CacheFileTimeout"
0x18002d396  jmp     loc_18002D2A8
0x18002d39b  lea     rdx, aDormantfilelim; "DormantFileLimit"
0x18002d3a2  jmp     loc_18002D2A8
0x18002d3a7  lea     rdx, aPipemaximum; "PipeMaximum"
0x18002d3ae  jmp     loc_18002D2A8
0x18002d3b3  lea     rdx, aPipeincrement; "PipeIncrement"
0x18002d3ba  jmp     loc_18002D2A8
0x18002d3bf  lea     rdx, aLockmaximum; "LockMaximum"
0x18002d3c6  jmp     loc_18002D2A8
0x18002d3cb  lea     rdx, aLockincrement; "LockIncrement"
0x18002d3d2  jmp     loc_18002D2A8
0x18002d3d7  lea     rdx, aLockquota; "LockQuota"
0x18002d3de  jmp     loc_18002D2A8
0x18002d3e3  lea     rdx, aUseopportunist; "UseOpportunisticLocking"
0x18002d3ea  jmp     loc_18002D4CD
0x18002d3ef  mov     eax, 420h
0x18002d3f4  cmp     ebx, eax
0x18002d3f6  ja      short loc_18002D475
0x18002d3f8  jz      short loc_18002D46C
0x18002d3fa  sub     ebx, 419h
0x18002d400  jz      short loc_18002D463
0x18002d402  sub     ebx, 1
0x18002d405  jz      short loc_18002D45A
0x18002d407  sub     ebx, 1
0x18002d40a  jz      short loc_18002D451
0x18002d40c  sub     ebx, 1
0x18002d40f  jz      short loc_18002D448
0x18002d411  sub     ebx, 1
0x18002d414  jz      short loc_18002D43C
0x18002d416  sub     ebx, 1
0x18002d419  jz      short loc_18002D430
0x18002d41b  cmp     ebx, 1
0x18002d41e  jnz     loc_18002D4D8
0x18002d424  lea     rdx, aUserawwrite; "UseRawWrite"
0x18002d42b  jmp     loc_18002D4CD
0x18002d430  lea     rdx, aUserawread; "UseRawRead"
0x18002d437  jmp     loc_18002D4CD
0x18002d43c  lea     rdx, aUtilizentcachi; "UtilizeNtCaching"
0x18002d443  jmp     loc_18002D4CD
0x18002d448  lea     rdx, aUselockreadunl; "UseLockReadUnlock"
0x18002d44f  jmp     short loc_18002D4CD
0x18002d451  lea     rdx, aBufnamedpipes; "BufNamedPipes"
0x18002d458  jmp     short loc_18002D4CD
0x18002d45a  lea     rdx, aUseclosebehind; "UseCloseBehind"
0x18002d461  jmp     short loc_18002D4CD
0x18002d463  lea     rdx, aUseunlockbehin; "UseUnlockBehind"
0x18002d46a  jmp     short loc_18002D4CD
0x18002d46c  lea     rdx, aUsewriterawdat; "UseWriteRawData"
0x18002d473  jmp     short loc_18002D4CD
0x18002d475  sub     ebx, 421h
0x18002d47b  jz      short loc_18002D4C6
0x18002d47d  sub     ebx, 1
0x18002d480  jz      short loc_18002D4BD
0x18002d482  sub     ebx, 1
0x18002d485  jz      short loc_18002D4B4
0x18002d487  sub     ebx, 1
0x18002d48a  jz      short loc_18002D4AB
0x18002d48c  sub     ebx, 1
0x18002d48f  jz      short loc_18002D4A2
0x18002d491  cmp     ebx, 1
0x18002d494  jnz     short loc_18002D4D8
0x18002d496  lea     rdx, aReadaheadthrou; "ReadAheadThroughput"
0x18002d49d  jmp     loc_18002D2A8
0x18002d4a2  lea     rdx, aUse512bytemaxt; "Use512ByteMaxTransfer"
0x18002d4a9  jmp     short loc_18002D4CD
0x18002d4ab  lea     rdx, aForcecorecreat; "ForceCoreCreateMode"
0x18002d4b2  jmp     short loc_18002D4CD
0x18002d4b4  lea     rdx, aBufreadonlyfil; "BufReadOnlyFiles"
0x18002d4bb  jmp     short loc_18002D4CD
0x18002d4bd  lea     rdx, aBuffilesdenywr; "BufFilesDenyWrite"
0x18002d4c4  jmp     short loc_18002D4CD
0x18002d4c6  lea     rdx, aUseencryption; "UseEncryption"
0x18002d4cd  mov     r8d, [rsi]
0x18002d4d0  mov     rcx, rdi
0x18002d4d3  call    WsSetConfigBool
0x18002d4d8  test    rdi, rdi
0x18002d4db  jz      short loc_18002D4E5
0x18002d4dd  mov     rcx, rdi
0x18002d4e0  call    NetpCloseConfigData
0x18002d4e5  add     rsp, 38h
0x18002d4e9  pop     rdi
0x18002d4ea  pop     rsi
0x18002d4eb  pop     rbx
0x18002d4ec  pop     rbp
0x18002d4ed  retn
```
