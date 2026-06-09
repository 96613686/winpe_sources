# CreateMutexWrapperW

- ea: `0x180022bf8`
- end: `0x180022ca2`
- name: `CreateMutexWrapperW`
- size: `170`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bd30`
- `0x18001c350`
- `0x18001c780`
- `0x18001ca90`
- `0x18001cb20`
- `0x18001f020`

## callees

- `0x180022698`
- `0x180022b80`
- `0x180022bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180022c60`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180022c60`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022c7a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022c7a`

## pseudocode

```c
HANDLE __fastcall CreateMutexWrapperW(LPCWSTR lpName)
{
  struct _SECURITY_ATTRIBUTES *v2; // rbx
  struct _ACL *v3; // rdi
  HANDLE MutexW; // rax
  HANDLE v5; // rbx
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8; // [rsp+30h] [rbp-38h]
  _OWORD v9[2]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v10; // [rsp+58h] [rbp-10h]

  v7 = 0;
  v8 = 0;
  memset(v9, 0, sizeof(v9));
  v2 = 0;
  v10 = 0;
  v3 = BuildCustomizedSD(v9);
  if ( v3 )
  {
    LODWORD(v8) = 0;
    *((_QWORD *)&v7 + 1) = v9;
    v2 = (struct _SECURITY_ATTRIBUTES *)&v7;
    LODWORD(v7) = 24;
  }
  MutexW = CreateMutexW(v2, 0, lpName);
  v5 = MutexW;
  if ( MutexW )
    WaitForSingleObject(MutexW, 0xFFFFFFFF);
  FreeAdministratorSD(v3);
  return v5;
}

```

## disassembly

```asm
0x180022bf8  mov     r11, rsp
0x180022bfb  mov     [r11+8], rbx
0x180022bff  mov     [r11+10h], rsi
0x180022c03  push    rdi
0x180022c04  sub     rsp, 60h
0x180022c08  xorps   xmm1, xmm1
0x180022c0b  xor     eax, eax
0x180022c0d  xorps   xmm0, xmm0
0x180022c10  mov     rsi, rcx
0x180022c13  movups  [rsp+68h+var_48], xmm0
0x180022c18  lea     rcx, [r11-30h]; pSecurityDescriptor
0x180022c1c  mov     [r11-38h], rax
0x180022c20  movups  [rsp+68h+var_30], xmm1
0x180022c25  xor     ebx, ebx
0x180022c27  movups  [rsp+68h+var_20], xmm1
0x180022c2c  mov     [r11-10h], rax
0x180022c30  call    ?BuildCustomizedSD@@YAPEAXPEAX@Z; BuildCustomizedSD(void *)
0x180022c35  mov     rdi, rax
0x180022c38  test    rax, rax
0x180022c3b  jz      short loc_180022C58
0x180022c3d  lea     rax, [rsp+68h+var_30]
0x180022c42  mov     dword ptr [rsp+68h+var_38], ebx
0x180022c46  mov     qword ptr [rsp+68h+var_48+8], rax
0x180022c4b  lea     rbx, [rsp+68h+var_48]
0x180022c50  mov     dword ptr [rsp+68h+var_48], 18h
0x180022c58  mov     r8, rsi; lpName
0x180022c5b  xor     edx, edx; bInitialOwner
0x180022c5d  mov     rcx, rbx; lpMutexAttributes
0x180022c60  call    cs:__imp_CreateMutexW
0x180022c67  nop     dword ptr [rax+rax+00h]
0x180022c6c  mov     rbx, rax
0x180022c6f  test    rax, rax
0x180022c72  jz      short loc_180022C86
0x180022c74  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180022c77  mov     rcx, rax; hHandle
0x180022c7a  call    cs:__imp_WaitForSingleObject
0x180022c81  nop     dword ptr [rax+rax+00h]
0x180022c86  mov     rcx, rdi; lpMem
0x180022c89  call    ?FreeAdministratorSD@@YAXPEAX@Z; FreeAdministratorSD(void *)
0x180022c8e  mov     rsi, [rsp+68h+arg_8]
0x180022c93  mov     rax, rbx
0x180022c96  mov     rbx, [rsp+68h+arg_0]
0x180022c9b  add     rsp, 60h
0x180022c9f  pop     rdi
0x180022ca0  retn
```
