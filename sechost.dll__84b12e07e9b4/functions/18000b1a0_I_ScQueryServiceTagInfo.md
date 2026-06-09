# I_ScQueryServiceTagInfo

- ea: `0x18000b1a0`
- end: `0x18000b450`
- name: `I_ScQueryServiceTagInfo`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000b130`

## callees

- `0x18000b1a0`
- `0x18000b460`
- `0x18000b9a0`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b31c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b31c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b20f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b21d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b20f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b21d`
- `RPCRT4!NdrClientCall2` at `0x18000b2a9`
- `RPCRT4!NdrClientCall2` at `0x18000b2a9`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fbee`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fbee`

## pseudocode

```c
__int64 __fastcall I_ScQueryServiceTagInfo(__int64 a1, unsigned int a2, __int64 a3)
{
  SC_HANDLE v5; // rsi
  _QWORD *v6; // rcx
  DWORD LastError; // ebx
  void *v8; // rax
  unsigned int v10; // edx
  bool v11; // zf
  __int64 v12; // rax
  __int16 *v13; // rdx
  __int16 v14; // cx
  __int16 v15; // ax
  unsigned int v16; // edi
  HLOCAL hMem; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v18; // [rsp+88h] [rbp+10h]
  __int64 v19; // [rsp+90h] [rbp+18h]
  __int64 v20; // [rsp+98h] [rbp+20h] BYREF

  v19 = a3;
  v18 = a2;
  v5 = 0;
  v20 = 0;
  v6 = 0;
  hMem = 0;
  if ( a2 != 1 )
  {
    v10 = a2 - 2;
    if ( v10 )
    {
      if ( v10 != 1 )
      {
        LastError = 1237;
        goto LABEL_5;
      }
      if ( !a3 )
        goto LABEL_4;
      v11 = *(_QWORD *)(a3 + 8) == 0;
    }
    else
    {
      if ( !a3 || !*(_DWORD *)a3 || !*(_QWORD *)(a3 + 8) )
        goto LABEL_4;
      v11 = *(_QWORD *)(a3 + 24) == 0;
    }
    if ( v11 )
      goto LABEL_18;
LABEL_4:
    LastError = 87;
    goto LABEL_5;
  }
  if ( !a3 || !*(_DWORD *)a3 || !*(_DWORD *)(a3 + 4) || *(_QWORD *)(a3 + 16) )
    goto LABEL_4;
LABEL_18:
  v20 = a3;
  v5 = OpenSCManagerW(0, 0, 4u);
  if ( !v5 )
  {
    LastError = GetLastError();
    goto LABEL_25;
  }
  LastError = (unsigned int)NdrClientCall2(&pStubDescriptor, &byte_180060C94, v5, a2, &v20, &hMem).Pointer;
  if ( LastError )
    goto LABEL_25;
  if ( a2 == 1 )
  {
    v6 = hMem;
    if ( hMem )
    {
      v12 = *((_QWORD *)hMem + 1);
      if ( v12 )
      {
        *(_QWORD *)(a3 + 16) = v12;
        *(_DWORD *)(a3 + 8) = *(_DWORD *)v6;
        v6[1] = 0;
        v6 = hMem;
        goto LABEL_5;
      }
    }
    goto LABEL_29;
  }
  if ( a2 != 2 )
  {
    if ( a2 == 3 )
    {
      v6 = hMem;
      if ( hMem && *((_QWORD *)hMem + 1) && *(_DWORD *)hMem )
      {
        *(_QWORD *)(a3 + 8) = hMem;
        v6 = 0;
        hMem = 0;
        goto LABEL_5;
      }
LABEL_29:
      LastError = 13;
      goto LABEL_5;
    }
    goto LABEL_25;
  }
  v6 = hMem;
  if ( !hMem )
    goto LABEL_29;
  v13 = (__int16 *)*((_QWORD *)hMem + 1);
  if ( !v13 )
    goto LABEL_29;
  *(_QWORD *)(a3 + 24) = v13;
  *(_DWORD *)(a3 + 16) = *(_DWORD *)v6;
  v6[1] = 0;
  v14 = *v13;
  if ( !*v13 )
  {
LABEL_25:
    v6 = hMem;
    goto LABEL_5;
  }
  do
  {
    v15 = 0;
    if ( v14 != 47 )
      v15 = v14;
    *v13++ = v15;
    v14 = *v13;
  }
  while ( *v13 );
  v6 = hMem;
LABEL_5:
  if ( v5 )
  {
    CloseServiceHandle(v5);
    v6 = hMem;
  }
  if ( a2 == 1 )
  {
    if ( v6 )
    {
      v8 = (void *)v6[1];
      if ( !v8 )
      {
LABEL_11:
        LocalFree(v6);
        return LastError;
      }
LABEL_10:
      LocalFree(v8);
      v6 = hMem;
      goto LABEL_11;
    }
  }
  else
  {
    v16 = a2 - 2;
    if ( !v16 )
    {
      if ( !v6 )
        return LastError;
      v8 = (void *)v6[1];
      if ( !v8 )
        goto LABEL_11;
      goto LABEL_10;
    }
    if ( v16 == 1 && v6 )
      goto LABEL_11;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000b1a0  mov     rax, rsp
0x18000b1a3  mov     [rax+18h], r8
0x18000b1a7  mov     [rax+10h], edx
0x18000b1aa  mov     [rax+8], rcx
0x18000b1ae  push    rbx
0x18000b1af  push    rsi
0x18000b1b0  push    rdi
0x18000b1b1  push    r14
0x18000b1b3  sub     rsp, 58h
0x18000b1b7  mov     r14, r8
0x18000b1ba  mov     edi, edx
0x18000b1bc  xor     esi, esi
0x18000b1be  mov     [rax+20h], rsi
0x18000b1c2  xor     ecx, ecx; lpMachineName
0x18000b1c4  mov     [rax+8], rcx
0x18000b1c8  cmp     edx, 1
0x18000b1cb  jnz     short loc_18000B22F
0x18000b1cd  test    r8, r8
0x18000b1d0  jz      short loc_18000B1DB
0x18000b1d2  cmp     [r8], ecx
0x18000b1d5  jnz     loc_18000B331
0x18000b1db  mov     ebx, 57h ; 'W'
0x18000b1e0  test    rsi, rsi
0x18000b1e3  jz      short loc_18000B1F5
0x18000b1e5  mov     rcx, rsi; hSCObject
0x18000b1e8  call    CloseServiceHandle
0x18000b1ed  mov     rcx, [rsp+78h+hMem]
0x18000b1f5  cmp     edi, 1
0x18000b1f8  jnz     loc_18000B419
0x18000b1fe  test    rcx, rcx
0x18000b201  jz      short loc_18000B223
0x18000b203  mov     rax, [rcx+8]
0x18000b207  test    rax, rax
0x18000b20a  jz      short loc_18000B21D
0x18000b20c  mov     rcx, rax; hMem
0x18000b20f  call    cs:__imp_LocalFree
0x18000b215  mov     rcx, [rsp+78h+hMem]; hMem
0x18000b21d  call    cs:__imp_LocalFree
0x18000b223  mov     eax, ebx
0x18000b225  add     rsp, 58h
0x18000b229  pop     r14
0x18000b22b  pop     rdi
0x18000b22c  pop     rsi
0x18000b22d  pop     rbx
0x18000b22e  retn
0x18000b22f  sub     edx, 2
0x18000b232  jz      loc_18000B396
0x18000b238  cmp     edx, 1
0x18000b23b  jnz     loc_18000B38C
0x18000b241  test    r8, r8
0x18000b244  jz      short loc_18000B1DB
0x18000b246  cmp     [r8+8], rcx
0x18000b24a  jnz     short loc_18000B1DB
0x18000b24c  mov     [rsp+78h+arg_18], r8
0x18000b254  xor     edx, edx; lpDatabaseName
0x18000b256  mov     r8d, 4; dwDesiredAccess
0x18000b25c  call    OpenSCManagerW
0x18000b261  mov     rsi, rax
0x18000b264  mov     [rsp+78h+var_38], rax
0x18000b269  test    rax, rax
0x18000b26c  jz      loc_18000B31C
0x18000b272  mov     [rsp+78h+var_40], 0
0x18000b27b  lea     rax, [rsp+78h+hMem]
0x18000b283  mov     [rsp+78h+var_50], rax
0x18000b288  lea     rax, [rsp+78h+arg_18]
0x18000b290  mov     [rsp+78h+var_58], rax
0x18000b295  mov     r9d, edi
0x18000b298  mov     r8, rsi
0x18000b29b  lea     rdx, byte_180060C94; pFormat
0x18000b2a2  lea     rcx, pStubDescriptor; pStubDescriptor
0x18000b2a9  call    cs:__imp_NdrClientCall2
0x18000b2af  mov     rbx, rax
0x18000b2b2  mov     [rsp+78h+var_40], rax
0x18000b2b7  mov     [rsp+78h+var_48], eax
0x18000b2bb  jmp     short loc_18000B2DE
0x18000b2bd  mov     ecx, eax; unsigned int
0x18000b2bf  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18000b2c4  mov     ebx, eax
0x18000b2c6  mov     [rsp+78h+var_48], eax
0x18000b2ca  mov     r14, [rsp+78h+arg_10]
0x18000b2d2  mov     edi, [rsp+78h+arg_8]
0x18000b2d9  mov     rsi, [rsp+78h+var_38]
0x18000b2de  test    ebx, ebx
0x18000b2e0  jnz     short loc_18000B324
0x18000b2e2  cmp     edi, 1
0x18000b2e5  jnz     short loc_18000B354
0x18000b2e7  mov     rcx, [rsp+78h+hMem]
0x18000b2ef  test    rcx, rcx
0x18000b2f2  jz      short loc_18000B34A
0x18000b2f4  mov     rax, [rcx+8]
0x18000b2f8  test    rax, rax
0x18000b2fb  jz      short loc_18000B34A
0x18000b2fd  mov     [r14+10h], rax
0x18000b301  mov     eax, [rcx]
0x18000b303  mov     [r14+8], eax
0x18000b307  mov     qword ptr [rcx+8], 0
0x18000b30f  mov     rcx, [rsp+78h+hMem]
0x18000b317  jmp     loc_18000B1E0
0x18000b31c  call    cs:__imp_GetLastError
0x18000b322  mov     ebx, eax
0x18000b324  mov     rcx, [rsp+78h+hMem]
0x18000b32c  jmp     loc_18000B1E0
0x18000b331  cmp     [r8+4], ecx
0x18000b335  jz      loc_18000B1DB
0x18000b33b  cmp     [r8+10h], rcx
0x18000b33f  jz      loc_18000B24C
0x18000b345  jmp     loc_18000B1DB
0x18000b34a  mov     ebx, 0Dh
0x18000b34f  jmp     loc_18000B1E0
0x18000b354  mov     ecx, edi
0x18000b356  sub     ecx, 2
0x18000b359  jz      short loc_18000B3BB
0x18000b35b  cmp     ecx, 1
0x18000b35e  jnz     short loc_18000B324
0x18000b360  mov     rcx, [rsp+78h+hMem]
0x18000b368  test    rcx, rcx
0x18000b36b  jz      short loc_18000B34A
0x18000b36d  cmp     qword ptr [rcx+8], 0
0x18000b372  jz      short loc_18000B34A
0x18000b374  cmp     dword ptr [rcx], 0
0x18000b377  jz      short loc_18000B34A
0x18000b379  mov     [r14+8], rcx
0x18000b37d  xor     ecx, ecx
0x18000b37f  mov     [rsp+78h+hMem], rcx
0x18000b387  jmp     loc_18000B1E0
0x18000b38c  mov     ebx, 4D5h
0x18000b391  jmp     loc_18000B1E0
0x18000b396  test    r8, r8
0x18000b399  jz      loc_18000B1DB
0x18000b39f  cmp     [r8], ecx
0x18000b3a2  jz      loc_18000B1DB
0x18000b3a8  cmp     [r8+8], rcx
0x18000b3ac  jz      loc_18000B1DB
0x18000b3b2  cmp     [r8+18h], rcx
0x18000b3b6  jmp     loc_18000B24A
0x18000b3bb  mov     rcx, [rsp+78h+hMem]
0x18000b3c3  test    rcx, rcx
0x18000b3c6  jz      short loc_18000B34A
0x18000b3c8  mov     rdx, [rcx+8]
0x18000b3cc  test    rdx, rdx
0x18000b3cf  jz      loc_18000B34A
0x18000b3d5  mov     [r14+18h], rdx
0x18000b3d9  mov     eax, [rcx]
0x18000b3db  mov     [r14+10h], eax
0x18000b3df  mov     qword ptr [rcx+8], 0
0x18000b3e7  movzx   ecx, word ptr [rdx]
0x18000b3ea  test    cx, cx
0x18000b3ed  jz      loc_18000B324
0x18000b3f3  xor     eax, eax
0x18000b3f5  cmp     cx, 2Fh ; '/'
0x18000b3f9  cmovnz  ax, cx
0x18000b3fd  mov     [rdx], ax
0x18000b400  lea     rdx, [rdx+2]
0x18000b404  movzx   ecx, word ptr [rdx]
0x18000b407  test    cx, cx
0x18000b40a  jnz     short loc_18000B3F3
0x18000b40c  mov     rcx, [rsp+78h+hMem]
0x18000b414  jmp     loc_18000B1E0
0x18000b419  sub     edi, 2
0x18000b41c  jz      short loc_18000B435
0x18000b41e  cmp     edi, 1
0x18000b421  jnz     loc_18000B223
0x18000b427  test    rcx, rcx
0x18000b42a  jz      loc_18000B223
0x18000b430  jmp     loc_18000B21D
0x18000b435  test    rcx, rcx
0x18000b438  jz      loc_18000B223
0x18000b43e  mov     rax, [rcx+8]
0x18000b442  test    rax, rax
0x18000b445  jz      loc_18000B21D
0x18000b44b  jmp     loc_18000B20C
0x18004fbe0  push    rbp
0x18004fbe2  sub     rsp, 30h
0x18004fbe6  mov     rbp, rdx
0x18004fbe9  mov     rcx, [rcx]
0x18004fbec  mov     ecx, [rcx]; ExceptionCode
0x18004fbee  call    cs:__imp_I_RpcExceptionFilter
0x18004fbf4  nop
0x18004fbf5  add     rsp, 30h
0x18004fbf9  pop     rbp
0x18004fbfa  retn
```
