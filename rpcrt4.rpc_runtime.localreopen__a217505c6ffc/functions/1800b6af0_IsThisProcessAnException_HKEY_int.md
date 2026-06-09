# IsThisProcessAnException(HKEY__ *,int *)

- ea: `0x1800b6af0`
- end: `0x1800b6d0d`
- name: `?IsThisProcessAnException@@YAJPEAUHKEY__@@PEAH@Z`
- size: `541`
- prototype: `__int64 __fastcall(HKEY hkey, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800955b0`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800b6930`
- `0x1800b6af0`

## import_xrefs

- `ntdll!wcsrchr` at `0x1800b6bfd`
- `ntdll!wcsrchr` at `0x1800b6bfd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6b55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6b55`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800b6be6`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800b6be6`

## pseudocode

```c
__int64 __fastcall IsThisProcessAnException(HKEY hkey, int *a2)
{
  unsigned int v4; // edi
  void *pvData; // rbp
  int i; // r15d
  LSTATUS ValueW; // eax
  __int64 result; // rax
  const wchar_t *CommandLineW; // rbx
  wchar_t *v10; // rax
  int v11; // ecx
  unsigned __int16 *v12; // rsi
  unsigned __int16 *v13; // r12
  unsigned __int16 *v14; // rbx
  DWORD pcbData; // [rsp+98h] [rbp+10h] BYREF

  pcbData = 0;
  v4 = 0;
  *a2 = 0;
  pvData = 0;
  for ( i = 5; ; --i )
  {
    if ( i <= 0 )
      goto LABEL_11;
    ValueW = RegGetValueW(hkey, 0, L"ExtErrorInfoExceptions", 2u, 0, pvData, &pcbData);
    v4 = ValueW;
    if ( ValueW && ValueW != 234 )
    {
      v4 = ValueW != 2 ? 0xE : 0;
LABEL_11:
      if ( pvData )
        goto LABEL_12;
      goto LABEL_13;
    }
    if ( pvData )
      break;
LABEL_8:
    pvData = AllocWrapper(saturated_mul(pcbData, 2u));
    if ( !pvData )
      return 14;
  }
  if ( ValueW == 234 )
  {
    FreeWrapper(pvData);
    goto LABEL_8;
  }
  CommandLineW = GetCommandLineW();
  v10 = wcsrchr(CommandLineW, 0x5Cu);
  v11 = 0;
  v12 = 0;
  v13 = v10 + 1;
  if ( !v10 )
    v13 = (unsigned __int16 *)CommandLineW;
  v14 = (unsigned __int16 *)pvData;
  while ( 2 )
  {
    if ( *v14 )
    {
      if ( v11 )
      {
        if ( v11 == 1 )
        {
          if ( *v14 == 34 )
          {
            *v14 = 0;
            if ( (unsigned int)DoesThisProcessCmdLineStartWithThisString(v13, v12) )
              goto LABEL_28;
            v11 = 0;
          }
          goto LABEL_35;
        }
        if ( v11 != 2 )
        {
          if ( *v14 == 34 )
          {
            *v14 = 0;
            if ( (unsigned int)DoesThisProcessCmdLineStartWithThisString(v13, v12) )
              goto LABEL_28;
            v12 = v14 + 1;
            goto LABEL_34;
          }
          if ( *v14 == 32 )
          {
            *v14 = 0;
            if ( (unsigned int)DoesThisProcessCmdLineStartWithThisString(v13, v12) )
              goto LABEL_28;
LABEL_34:
            v11 = 3;
          }
LABEL_35:
          ++v14;
          continue;
        }
        if ( *v14 == 34 )
        {
          v12 = v14 + 1;
LABEL_31:
          v11 = 1;
          goto LABEL_35;
        }
        if ( *v14 == 32 )
          goto LABEL_35;
      }
      else
      {
        if ( *v14 == 34 )
        {
          v12 = v14;
          goto LABEL_31;
        }
        if ( *v14 == 32 )
        {
          v11 = 2;
          goto LABEL_35;
        }
      }
      v12 = v14;
      goto LABEL_34;
    }
    break;
  }
  if ( v12 && (unsigned int)DoesThisProcessCmdLineStartWithThisString(v13, v12) )
LABEL_28:
    *a2 = 1;
LABEL_12:
  FreeWrapper(pvData);
LABEL_13:
  result = v4;
  if ( !i )
    return 1766;
  return result;
}

```

## disassembly

```asm
0x1800b6af0  mov     rax, rsp
0x1800b6af3  push    rbx
0x1800b6af4  push    rbp
0x1800b6af5  push    rsi
0x1800b6af6  push    rdi
0x1800b6af7  push    r12
0x1800b6af9  push    r13
0x1800b6afb  push    r14
0x1800b6afd  push    r15
0x1800b6aff  sub     rsp, 48h
0x1800b6b03  xor     r13d, r13d
0x1800b6b06  mov     r14, rdx
0x1800b6b09  mov     rbx, rcx
0x1800b6b0c  mov     [rax+10h], r13d
0x1800b6b10  mov     edi, r13d
0x1800b6b13  mov     [rdx], r13d
0x1800b6b16  mov     ebp, r13d
0x1800b6b19  mov     esi, 0EAh
0x1800b6b1e  lea     r15d, [r13+5]
0x1800b6b22  lea     r12d, [r13+2]
0x1800b6b26  test    r15d, r15d
0x1800b6b29  jle     loc_1800B6BBA
0x1800b6b2f  lea     rax, [rsp+88h+arg_8]
0x1800b6b37  mov     r9d, r12d; dwFlags
0x1800b6b3a  mov     [rsp+88h+pcbData], rax; pcbData
0x1800b6b3f  lea     r8, aExterrorinfoex; "ExtErrorInfoExceptions"
0x1800b6b46  mov     [rsp+88h+pvData], rbp; pvData
0x1800b6b4b  xor     edx, edx; lpSubKey
0x1800b6b4d  mov     rcx, rbx; hkey
0x1800b6b50  mov     [rsp+88h+pdwType], r13; pdwType
0x1800b6b55  call    cs:__imp_RegGetValueW
0x1800b6b5c  nop     dword ptr [rax+rax+00h]
0x1800b6b61  mov     edi, eax
0x1800b6b63  test    eax, eax
0x1800b6b65  jz      short loc_1800B6B6B
0x1800b6b67  cmp     eax, esi
0x1800b6b69  jnz     short loc_1800B6BB0
0x1800b6b6b  test    rbp, rbp
0x1800b6b6e  jz      short loc_1800B6B7C
0x1800b6b70  cmp     edi, esi
0x1800b6b72  jnz     short loc_1800B6BE6
0x1800b6b74  mov     rcx, rbp; lpMem
0x1800b6b77  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b6b7c  mov     ecx, [rsp+88h+arg_8]
0x1800b6b83  mov     rax, r12
0x1800b6b86  mul     rcx
0x1800b6b89  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b6b90  cmovb   rax, rcx
0x1800b6b94  mov     rcx, rax; dwBytes
0x1800b6b97  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800b6b9c  mov     rbp, rax
0x1800b6b9f  test    rax, rax
0x1800b6ba2  jz      loc_1800B6D03
0x1800b6ba8  dec     r15d
0x1800b6bab  jmp     loc_1800B6B26
0x1800b6bb0  sub     edi, r12d
0x1800b6bb3  neg     edi
0x1800b6bb5  sbb     edi, edi
0x1800b6bb7  and     edi, 0Eh
0x1800b6bba  test    rbp, rbp
0x1800b6bbd  jz      short loc_1800B6BC7
0x1800b6bbf  mov     rcx, rbp; lpMem
0x1800b6bc2  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b6bc7  test    r15d, r15d
0x1800b6bca  mov     eax, edi
0x1800b6bcc  mov     ecx, 6E6h
0x1800b6bd1  cmovz   eax, ecx
0x1800b6bd4  add     rsp, 48h
0x1800b6bd8  pop     r15
0x1800b6bda  pop     r14
0x1800b6bdc  pop     r13
0x1800b6bde  pop     r12
0x1800b6be0  pop     rdi
0x1800b6be1  pop     rsi
0x1800b6be2  pop     rbp
0x1800b6be3  pop     rbx
0x1800b6be4  retn
0x1800b6be6  call    cs:__imp_GetCommandLineW
0x1800b6bed  nop     dword ptr [rax+rax+00h]
0x1800b6bf2  mov     rcx, rax; Str
0x1800b6bf5  mov     edx, 5Ch ; '\'; Ch
0x1800b6bfa  mov     rbx, rax
0x1800b6bfd  call    cs:__imp_wcsrchr
0x1800b6c04  nop     dword ptr [rax+rax+00h]
0x1800b6c09  mov     ecx, r13d
0x1800b6c0c  mov     rsi, r13
0x1800b6c0f  test    rax, rax
0x1800b6c12  lea     r12, [rax+2]
0x1800b6c16  cmovz   r12, rbx
0x1800b6c1a  mov     rbx, rbp
0x1800b6c1d  cmp     [rbx], r13w
0x1800b6c21  jz      loc_1800B6CE2
0x1800b6c27  mov     edx, ecx
0x1800b6c29  test    ecx, ecx
0x1800b6c2b  jz      loc_1800B6CCA
0x1800b6c31  sub     edx, 1
0x1800b6c34  jz      short loc_1800B6CAC
0x1800b6c36  sub     edx, 1
0x1800b6c39  jz      short loc_1800B6C84
0x1800b6c3b  cmp     edx, 1
0x1800b6c3e  jnz     short loc_1800B6CA3
0x1800b6c40  cmp     word ptr [rbx], 22h ; '"'
0x1800b6c44  jnz     short loc_1800B6C5F
0x1800b6c46  mov     rdx, rsi; unsigned __int16 *
0x1800b6c49  mov     [rbx], r13w
0x1800b6c4d  mov     rcx, r12; unsigned __int16 *
0x1800b6c50  call    ?DoesThisProcessCmdLineStartWithThisString@@YAHPEAG0@Z; DoesThisProcessCmdLineStartWithThisString(ushort *,ushort *)
0x1800b6c55  test    eax, eax
0x1800b6c57  jnz     short loc_1800B6C78
0x1800b6c59  lea     rsi, [rbx+2]
0x1800b6c5d  jmp     short loc_1800B6C9E
0x1800b6c5f  cmp     word ptr [rbx], 20h ; ' '
0x1800b6c63  jnz     short loc_1800B6CA3
0x1800b6c65  mov     rdx, rsi; unsigned __int16 *
0x1800b6c68  mov     [rbx], r13w
0x1800b6c6c  mov     rcx, r12; unsigned __int16 *
0x1800b6c6f  call    ?DoesThisProcessCmdLineStartWithThisString@@YAHPEAG0@Z; DoesThisProcessCmdLineStartWithThisString(ushort *,ushort *)
0x1800b6c74  test    eax, eax
0x1800b6c76  jz      short loc_1800B6C9E
0x1800b6c78  mov     dword ptr [r14], 1
0x1800b6c7f  jmp     loc_1800B6BBF
0x1800b6c84  cmp     word ptr [rbx], 22h ; '"'
0x1800b6c88  jnz     short loc_1800B6C95
0x1800b6c8a  lea     rsi, [rbx+2]
0x1800b6c8e  mov     ecx, 1
0x1800b6c93  jmp     short loc_1800B6CA3
0x1800b6c95  cmp     word ptr [rbx], 20h ; ' '
0x1800b6c99  jz      short loc_1800B6CA3
0x1800b6c9b  mov     rsi, rbx
0x1800b6c9e  mov     ecx, 3
0x1800b6ca3  add     rbx, 2
0x1800b6ca7  jmp     loc_1800B6C1D
0x1800b6cac  cmp     word ptr [rbx], 22h ; '"'
0x1800b6cb0  jnz     short loc_1800B6CA3
0x1800b6cb2  mov     rdx, rsi; unsigned __int16 *
0x1800b6cb5  mov     [rbx], r13w
0x1800b6cb9  mov     rcx, r12; unsigned __int16 *
0x1800b6cbc  call    ?DoesThisProcessCmdLineStartWithThisString@@YAHPEAG0@Z; DoesThisProcessCmdLineStartWithThisString(ushort *,ushort *)
0x1800b6cc1  test    eax, eax
0x1800b6cc3  jnz     short loc_1800B6C78
0x1800b6cc5  mov     ecx, r13d
0x1800b6cc8  jmp     short loc_1800B6CA3
0x1800b6cca  cmp     word ptr [rbx], 22h ; '"'
0x1800b6cce  jnz     short loc_1800B6CD5
0x1800b6cd0  mov     rsi, rbx
0x1800b6cd3  jmp     short loc_1800B6C8E
0x1800b6cd5  cmp     word ptr [rbx], 20h ; ' '
0x1800b6cd9  jnz     short loc_1800B6C9B
0x1800b6cdb  mov     ecx, 2
0x1800b6ce0  jmp     short loc_1800B6CA3
0x1800b6ce2  test    rsi, rsi
0x1800b6ce5  jz      loc_1800B6BBF
0x1800b6ceb  mov     rdx, rsi; unsigned __int16 *
0x1800b6cee  mov     rcx, r12; unsigned __int16 *
0x1800b6cf1  call    ?DoesThisProcessCmdLineStartWithThisString@@YAHPEAG0@Z; DoesThisProcessCmdLineStartWithThisString(ushort *,ushort *)
0x1800b6cf6  test    eax, eax
0x1800b6cf8  jz      loc_1800B6BBF
0x1800b6cfe  jmp     loc_1800B6C78
0x1800b6d03  mov     eax, 0Eh
0x1800b6d08  jmp     loc_1800B6BD4
```
