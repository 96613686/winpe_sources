# LsaClose

- ea: `0x18000f490`
- end: `0x18000f4f6`
- name: `LsaClose`
- size: `102`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE ObjectHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000f1a0`

## callees

- `0x18000f490`
- `0x18000f4fc`
- `0x180016afc`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180022422`
- `RPCRT4!I_RpcExceptionFilter` at `0x180022422`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000f4c9`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000f4c9`

## pseudocode

```c
NTSTATUS __stdcall LsaClose(LSA_HANDLE ObjectHandle)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  NTSTATUS v4; // [rsp+20h] [rbp-18h]
  LSA_HANDLE v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = ObjectHandle;
  if ( !ObjectHandle )
    return -1073741816;
  if ( *(_DWORD *)ObjectHandle != 1431128404 )
    return -1073741816;
  v4 = LsarClose((char *)ObjectHandle + 8);
  LsapFreePrivateHandle(&v5, v2, v3);
  return v4;
}

```

## disassembly

```asm
0x18000f490  push    rbx
0x18000f492  sub     rsp, 30h
0x18000f496  mov     [rsp+38h+arg_0], rcx
0x18000f49b  test    rcx, rcx
0x18000f49e  jnz     short loc_18000F4A7
0x18000f4a0  mov     eax, 0C0000008h
0x18000f4a5  jmp     short loc_18000F4F0
0x18000f4a7  cmp     dword ptr [rcx], 554D4954h
0x18000f4ad  jz      short loc_18000F4B6
0x18000f4af  mov     eax, 0C0000008h
0x18000f4b4  jmp     short loc_18000F4F0
0x18000f4b6  add     rcx, 8
0x18000f4ba  call    LsarClose
0x18000f4bf  mov     ebx, eax
0x18000f4c1  mov     [rsp+38h+var_18], eax
0x18000f4c5  jmp     short loc_18000F4DD
0x18000f4c7  mov     ecx, eax; Status
0x18000f4c9  call    cs:__imp_I_RpcMapWin32Status
0x18000f4cf  mov     ebx, 0C0000001h
0x18000f4d4  test    eax, eax
0x18000f4d6  cmovs   ebx, eax
0x18000f4d9  mov     [rsp+38h+var_18], ebx
0x18000f4dd  lea     rcx, [rsp+38h+arg_0]
0x18000f4e2  call    LsapFreePrivateHandle
0x18000f4e7  mov     eax, ebx
0x18000f4e9  jmp     short loc_18000F4F0
0x18000f4eb  mov     eax, 0C0000008h
0x18000f4f0  add     rsp, 30h
0x18000f4f4  pop     rbx
0x18000f4f5  retn
0x180022414  push    rbp
0x180022416  sub     rsp, 20h
0x18002241a  mov     rbp, rdx
0x18002241d  mov     rcx, [rcx]
0x180022420  mov     ecx, [rcx]; ExceptionCode
0x180022422  call    cs:__imp_I_RpcExceptionFilter
0x180022428  nop
0x180022429  add     rsp, 20h
0x18002242d  pop     rbp
0x18002242e  retn
```
