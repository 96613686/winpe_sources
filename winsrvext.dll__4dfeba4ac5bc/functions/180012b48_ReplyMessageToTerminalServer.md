# ReplyMessageToTerminalServer

- ea: `0x180012b48`
- end: `0x180012c53`
- name: `ReplyMessageToTerminalServer`
- size: `267`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000d030`
- `0x180010420`
- `0x180011de4`

## callees

- `0x1800129f8`
- `0x180012b48`
- `0x1800138c5`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180012b87`
- `KERNELBASE!LocalAlloc` at `0x180012b87`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180012c15`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180012c15`
- `ntdll!NtClose` at `0x180012c28`
- `ntdll!NtClose` at `0x180012c28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012c37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012c37`

## pseudocode

```c
__int64 __fastcall ReplyMessageToTerminalServer(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  int v8; // r14d
  __int64 result; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  unsigned int v12; // ebx
  HANDLE Handle[9]; // [rsp+40h] [rbp-48h] BYREF

  Handle[0] = 0;
  v8 = a1;
  result = ConnectToTerminalServer(a1, Handle);
  if ( (int)result >= 0 )
  {
    v10 = LocalAlloc(0, 0x4070u);
    v11 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, 0x4070u);
      v11[9] = a5;
      *(_DWORD *)v11 = 1081098312;
      *((_BYTE *)v11 + 48) = 1;
      *((_DWORD *)v11 + 11) = 2;
      *((_DWORD *)v11 + 13) = 0;
      *((_DWORD *)v11 + 14) = a3;
      v11[8] = a4;
      *((_DWORD *)v11 + 20) = v8;
      v11[11] = a2;
      v12 = NtAlpcSendWaitReceivePort(Handle[0], 0x20000, v11, 0, v11, 0, 0, 0);
      NtClose(Handle[0]);
      LocalFree(v11);
      return v12;
    }
    else
    {
      return 3221225495LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012b48  push    rbx
0x180012b4a  push    rbp
0x180012b4b  push    rsi
0x180012b4c  push    rdi
0x180012b4d  push    r12
0x180012b4f  push    r14
0x180012b51  sub     rsp, 58h
0x180012b55  mov     rbp, rdx
0x180012b58  mov     [rsp+88h+Handle], 0
0x180012b61  lea     rdx, [rsp+88h+Handle]
0x180012b66  mov     rbx, r9
0x180012b69  mov     esi, r8d
0x180012b6c  mov     r14d, ecx
0x180012b6f  call    ConnectToTerminalServer
0x180012b74  test    eax, eax
0x180012b76  js      loc_180012C45
0x180012b7c  mov     r12d, 4070h
0x180012b82  xor     ecx, ecx; uFlags
0x180012b84  mov     edx, r12d; uBytes
0x180012b87  call    cs:__imp_LocalAlloc
0x180012b8e  nop     dword ptr [rax+rax+00h]
0x180012b93  mov     rdi, rax
0x180012b96  test    rax, rax
0x180012b99  jnz     short loc_180012BA5
0x180012b9b  mov     eax, 0C0000017h
0x180012ba0  jmp     loc_180012C45
0x180012ba5  mov     r8, r12; Size
0x180012ba8  xor     edx, edx; Val
0x180012baa  mov     rcx, rdi; void *
0x180012bad  call    memset_0
0x180012bb2  mov     rax, [rsp+88h+arg_20]
0x180012bba  xor     r9d, r9d
0x180012bbd  mov     [rsp+88h+var_50], 0
0x180012bc6  mov     r8, rdi
0x180012bc9  mov     [rdi+48h], rax
0x180012bcd  mov     edx, 20000h
0x180012bd2  mov     dword ptr [rdi], 40704048h
0x180012bd8  mov     byte ptr [rdi+30h], 1
0x180012bdc  mov     dword ptr [rdi+2Ch], 2
0x180012be3  mov     dword ptr [rdi+34h], 0
0x180012bea  mov     [rdi+38h], esi
0x180012bed  mov     [rdi+40h], rbx
0x180012bf1  mov     [rdi+50h], r14d
0x180012bf5  mov     [rdi+58h], rbp
0x180012bf9  mov     rcx, [rsp+88h+Handle]
0x180012bfe  mov     [rsp+88h+var_58], 0
0x180012c07  mov     [rsp+88h+var_60], 0
0x180012c10  mov     [rsp+88h+var_68], rdi
0x180012c15  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180012c1c  nop     dword ptr [rax+rax+00h]
0x180012c21  mov     rcx, [rsp+88h+Handle]; Handle
0x180012c26  mov     ebx, eax
0x180012c28  call    cs:__imp_NtClose
0x180012c2f  nop     dword ptr [rax+rax+00h]
0x180012c34  mov     rcx, rdi; hMem
0x180012c37  call    cs:__imp_LocalFree
0x180012c3e  nop     dword ptr [rax+rax+00h]
0x180012c43  mov     eax, ebx
0x180012c45  add     rsp, 58h
0x180012c49  pop     r14
0x180012c4b  pop     r12
0x180012c4d  pop     rdi
0x180012c4e  pop     rsi
0x180012c4f  pop     rbp
0x180012c50  pop     rbx
0x180012c51  retn
```
