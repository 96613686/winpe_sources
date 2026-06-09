# LsaRevertSecurityContext(_SecHandle *)

- ea: `0x180014fa0`
- end: `0x180015009`
- name: `?LsaRevertSecurityContext@@YAJPEAU_SecHandle@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(struct _SecHandle *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014fa0`
- `0x18001c948`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x180014fc5`
- `ntdll!NtSetInformationThread` at `0x180014fc5`

## pseudocode

```c
__int64 __fastcall LsaRevertSecurityContext(struct _SecHandle *a1)
{
  NTSTATUS v1; // ebx
  __int64 v2; // r8
  __int64 ThreadInformation; // [rsp+48h] [rbp+10h] BYREF

  ThreadInformation = 0;
  v1 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  if ( v1 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v2, ThreadInformation, v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180014fa0  push    rbx
0x180014fa2  sub     rsp, 30h
0x180014fa6  mov     r9d, 8; ThreadInformationLength
0x180014fac  mov     [rsp+38h+ThreadInformation], 0
0x180014fb5  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x180014fba  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180014fc1  lea     edx, [r9-3]; ThreadInformationClass
0x180014fc5  call    cs:__imp_NtSetInformationThread
0x180014fcb  mov     ebx, eax
0x180014fcd  test    eax, eax
0x180014fcf  jns     short loc_180015001
0x180014fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fd8  lea     rax, WPP_GLOBAL_Control
0x180014fdf  cmp     rcx, rax
0x180014fe2  jz      short loc_180015001
0x180014fe4  test    byte ptr [rcx+1Ch], 1
0x180014fe8  jz      short loc_180015001
0x180014fea  mov     r9, [rsp+38h+ThreadInformation]
0x180014fef  mov     edx, 10h
0x180014ff4  mov     rcx, [rcx+10h]
0x180014ff8  mov     [rsp+38h+var_18], ebx
0x180014ffc  call    WPP_SF_qD
0x180015001  mov     eax, ebx
0x180015003  add     rsp, 30h
0x180015007  pop     rbx
0x180015008  retn
```
