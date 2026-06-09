# SclRegDeleteKeyRecursive

- ea: `0x180008e40`
- end: `0x180008fe7`
- name: `SclRegDeleteKeyRecursive`
- size: `423`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180004428`
- `0x1800088bc`
- `0x180008e40`
- `0x180009cd0`
- `0x18000d620`

## callees

- `0x1800014e8`
- `0x180008d44`
- `0x180008e40`
- `0x1800091c0`
- `0x18000a524`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180008e7d`
- `ntdll!RtlAllocateHeap` at `0x180008e7d`
- `ntdll!NtClose` at `0x180008f6d`
- `ntdll!NtClose` at `0x180008f7b`
- `ntdll!NtClose` at `0x180008f6d`
- `ntdll!NtClose` at `0x180008f7b`
- `ntdll!RtlFreeHeap` at `0x180008fd2`
- `ntdll!RtlFreeHeap` at `0x180008fd2`

## string_xrefs

- `0x180008e94`: `(%lx): Failed to open subkey '%ws'`
- `0x180008ed0`: `(%lx): Failed to open subkey '%ws'`
- `0x180008fa3`: `SclRegDeleteKeyRecursive`
- `0x180008f81`: `(%lx): Unable to recursively delete subkey '%ws'`

## pseudocode

```c
__int64 __fastcall SclRegDeleteKeyRecursive(__int64 a1, const WCHAR *a2)
{
  PVOID v4; // rdi
  NTSTATUS v5; // ebx
  char *v6; // rax
  int v7; // r9d
  int Key; // eax
  int v9; // r8d
  int v10; // eax
  int v11; // edx
  __int64 v12; // rcx
  char *v13; // rdx
  __int64 v15; // [rsp+30h] [rbp-20h]
  HANDLE Handle; // [rsp+40h] [rbp-10h] BYREF
  PVOID P; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+30h] BYREF
  int v19; // [rsp+88h] [rbp+38h] BYREF

  Handle = 0;
  v19 = 0;
  v18 = 2064;
  P = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x810u);
  v4 = P;
  if ( P )
  {
    Key = SclCreateKey(a1, a2, 0xF003Fu, (__int64)&Handle);
    v5 = Key;
    if ( Key < 0 )
    {
      SclLogGenericMessage(
        0,
        3,
        (int)SclEvent_Generic_Error,
        174,
        (__int64)"SclRegDeleteKeyRecursive",
        "(%lx): Failed to open subkey '%ws'",
        Key,
        a2);
      goto LABEL_19;
    }
    while ( 1 )
    {
      v10 = SclRegEnumerateKey((_DWORD)Handle, 0, v9, (unsigned int)&P, (__int64)&v18, 2, (__int64)&v19);
      v4 = P;
      v5 = v10;
      if ( v10 == -2147483622 )
        break;
      if ( v10 < 0 )
        goto LABEL_11;
      v11 = *((_DWORD *)P + 3);
      if ( (unsigned __int64)(unsigned int)(v11 + 16) + 2 > v18 )
      {
        v5 = -2147483643;
LABEL_11:
        SclRegDeleteKey(Handle);
        goto LABEL_13;
      }
      v12 = v11 & 0xFFFFFFFE;
      v13 = (char *)P + 16;
      *(_WORD *)((char *)P + v12 + 16) = 0;
      v5 = SclRegDeleteKeyRecursive(Handle, v13);
      if ( v5 < 0 )
        goto LABEL_11;
    }
    v5 = SclRegDeleteKey(Handle);
LABEL_13:
    if ( v5 < 0 )
    {
      NtClose(Handle);
    }
    else
    {
      v5 = NtClose(Handle);
      if ( v5 >= 0 )
        goto LABEL_19;
    }
    v6 = "(%lx): Unable to recursively delete subkey '%ws'";
    v7 = 234;
  }
  else
  {
    v5 = -1073741801;
    v6 = "(%lx): Failed to open subkey '%ws'";
    v7 = 161;
  }
  LODWORD(v15) = v5;
  SclLogGenericMessage(0, 3, (int)SclEvent_Generic_Error, v7, (__int64)"SclRegDeleteKeyRecursive", v6, v15, a2);
LABEL_19:
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008e40  mov     [rsp-18h+arg_0], rbx
0x180008e45  push    rbp
0x180008e46  push    rsi
0x180008e47  push    rdi
0x180008e48  mov     rbp, rsp
0x180008e4b  sub     rsp, 50h
0x180008e4f  mov     rbx, rcx
0x180008e52  mov     [rbp+Handle], 0
0x180008e5a  mov     rcx, gs:60h
0x180008e63  mov     rsi, rdx
0x180008e66  mov     r8d, 810h; Size
0x180008e6c  mov     [rbp+arg_18], 0
0x180008e73  xor     edx, edx; Flags
0x180008e75  mov     [rbp+arg_10], r8d
0x180008e79  mov     rcx, [rcx+30h]; HeapHandle
0x180008e7d  call    cs:__imp_RtlAllocateHeap
0x180008e83  mov     [rbp+P], rax
0x180008e87  mov     rdi, rax
0x180008e8a  test    rax, rax
0x180008e8d  jnz     short loc_180008EA6
0x180008e8f  mov     ebx, 0C0000017h
0x180008e94  lea     rax, aLxFailedToOpen_2; "(%lx): Failed to open subkey '%ws'"
0x180008e9b  mov     r9d, 0A1h
0x180008ea1  jmp     loc_180008F8E
0x180008ea6  lea     r9, [rbp+Handle]
0x180008eaa  mov     r8d, 0F003Fh
0x180008eb0  mov     rdx, rsi
0x180008eb3  mov     rcx, rbx
0x180008eb6  call    SclCreateKey
0x180008ebb  mov     ebx, eax
0x180008ebd  test    eax, eax
0x180008ebf  jns     short loc_180008EDC
0x180008ec1  mov     [rsp+50h+var_18], rsi
0x180008ec6  mov     r9d, 0AEh
0x180008ecc  mov     dword ptr [rsp+50h+var_20], eax
0x180008ed0  lea     rax, aLxFailedToOpen_2; "(%lx): Failed to open subkey '%ws'"
0x180008ed7  jmp     loc_180008F97
0x180008edc  mov     rcx, [rbp+Handle]
0x180008ee0  lea     rax, [rbp+arg_18]
0x180008ee4  mov     [rsp+50h+var_20], rax
0x180008ee9  lea     r9, [rbp+P]
0x180008eed  lea     rax, [rbp+arg_10]
0x180008ef1  mov     dword ptr [rsp+50h+var_28], 2
0x180008ef9  xor     edx, edx
0x180008efb  mov     [rsp+50h+var_30], rax
0x180008f00  call    SclRegEnumerateKey
0x180008f05  mov     rdi, [rbp+P]
0x180008f09  mov     ebx, eax
0x180008f0b  cmp     eax, 8000001Ah
0x180008f10  jz      short loc_180008F5A
0x180008f12  test    eax, eax
0x180008f14  js      short loc_180008F4F
0x180008f16  mov     edx, [rdi+0Ch]
0x180008f19  mov     eax, [rbp+arg_10]
0x180008f1c  lea     ecx, [rdx+10h]
0x180008f1f  add     rcx, 2
0x180008f23  cmp     rcx, rax
0x180008f26  ja      short loc_180008F4A
0x180008f28  mov     ecx, edx
0x180008f2a  xor     eax, eax
0x180008f2c  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180008f30  lea     rdx, [rdi+10h]
0x180008f34  mov     [rcx+rdi+10h], ax
0x180008f39  mov     rcx, [rbp+Handle]
0x180008f3d  call    SclRegDeleteKeyRecursive
0x180008f42  mov     ebx, eax
0x180008f44  test    eax, eax
0x180008f46  jns     short loc_180008EDC
0x180008f48  jmp     short loc_180008F4F
0x180008f4a  mov     ebx, 80000005h
0x180008f4f  mov     rcx, [rbp+Handle]; Handle
0x180008f53  call    SclRegDeleteKey
0x180008f58  jmp     short loc_180008F65
0x180008f5a  mov     rcx, [rbp+Handle]; Handle
0x180008f5e  call    SclRegDeleteKey
0x180008f63  mov     ebx, eax
0x180008f65  mov     rcx, [rbp+Handle]; Handle
0x180008f69  test    ebx, ebx
0x180008f6b  js      short loc_180008F7B
0x180008f6d  call    cs:__imp_NtClose
0x180008f73  mov     ebx, eax
0x180008f75  test    eax, eax
0x180008f77  jns     short loc_180008FBB
0x180008f79  jmp     short loc_180008F81
0x180008f7b  call    cs:__imp_NtClose
0x180008f81  lea     rax, aLxUnableToRecu; "(%lx): Unable to recursively delete sub"...
0x180008f88  mov     r9d, 0EAh
0x180008f8e  mov     [rsp+50h+var_18], rsi
0x180008f93  mov     dword ptr [rsp+50h+var_20], ebx
0x180008f97  mov     [rsp+50h+var_28], rax
0x180008f9c  lea     r8, SclEvent_Generic_Error
0x180008fa3  lea     rax, aSclregdeleteke; "SclRegDeleteKeyRecursive"
0x180008faa  mov     edx, 3
0x180008faf  xor     ecx, ecx
0x180008fb1  mov     [rsp+50h+var_30], rax
0x180008fb6  call    SclLogGenericMessage
0x180008fbb  test    rdi, rdi
0x180008fbe  jz      short loc_180008FD8
0x180008fc0  mov     rcx, gs:60h
0x180008fc9  mov     r8, rdi; P
0x180008fcc  xor     edx, edx; Flags
0x180008fce  mov     rcx, [rcx+30h]; HeapHandle
0x180008fd2  call    cs:__imp_RtlFreeHeap
0x180008fd8  mov     eax, ebx
0x180008fda  mov     rbx, [rsp+50h+arg_0]
0x180008fdf  add     rsp, 50h
0x180008fe3  pop     rdi
0x180008fe4  pop     rsi
0x180008fe5  pop     rbp
0x180008fe6  retn
```
