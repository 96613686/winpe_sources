# OncRpcWiMgrpWorkerThreadCreate

- ea: `0x1400203a4`
- end: `0x1400204b9`
- name: `OncRpcWiMgrpWorkerThreadCreate`
- size: `277`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000f318`
- `0x14000f490`

## callees

- `0x1400020c0`
- `0x1400203a4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140020449`
- `ntoskrnl!ZwClose` at `0x140020449`
- `ntoskrnl!PsCreateSystemThread` at `0x140020433`
- `ntoskrnl!PsCreateSystemThread` at `0x140020433`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020466`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020466`

## pseudocode

```c
__int64 __fastcall OncRpcWiMgrpWorkerThreadCreate(__int64 *P)
{
  __int64 v2; // rcx
  NTSTATUS v3; // edi
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+80h] [rbp+10h] BYREF

  ThreadHandle = 0;
  v2 = *P;
  memset(&ObjectAttributes, 0, 44);
  if ( (*(_DWORD *)(v2 + 216) & 1) != 0 )
  {
    v3 = -1073741077;
LABEL_6:
    ExFreePoolWithTag(P, 0x52505452u);
    goto LABEL_7;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v2 + 104));
  v3 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, &ObjectAttributes, 0, 0, (PKSTART_ROUTINE)OncRpcWiMgrpWorker, P);
  if ( v3 < 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(*P + 104));
    goto LABEL_6;
  }
  ZwClose(ThreadHandle);
LABEL_7:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400203a4  mov     [rsp-8+arg_8], rbx
0x1400203a9  mov     [rsp-8+arg_10], rdi
0x1400203ae  push    rbp
0x1400203af  mov     rbp, rsp
0x1400203b2  sub     rsp, 70h
0x1400203b6  xorps   xmm0, xmm0
0x1400203b9  xor     eax, eax
0x1400203bb  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400203bf  mov     rbx, rcx
0x1400203c2  mov     [rbp+ThreadHandle], rax
0x1400203c6  mov     rcx, [rcx]
0x1400203c9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400203cd  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400203d1  mov     eax, [rcx+0D8h]
0x1400203d7  test    al, 1
0x1400203d9  jz      short loc_1400203E2
0x1400203db  mov     edi, 0C00002EBh
0x1400203e0  jmp     short loc_14002045E
0x1400203e2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400203e9  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400203f1  mov     [rbp+ObjectAttributes.Attributes], 200h
0x1400203f8  mov     [rbp+ObjectAttributes.ObjectName], 0
0x140020400  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140020405  lock inc dword ptr [rcx+68h]
0x140020409  lea     rax, OncRpcWiMgrpWorker
0x140020410  mov     [rsp+70h+StartContext], rbx; StartContext
0x140020415  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x14002041a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002041e  xor     r9d, r9d; ProcessHandle
0x140020421  mov     [rsp+70h+ClientId], 0; ClientId
0x14002042a  mov     edx, 1FFFFFh; DesiredAccess
0x14002042f  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x140020433  call    cs:__imp_PsCreateSystemThread
0x14002043a  nop     dword ptr [rax+rax+00h]
0x14002043f  mov     edi, eax
0x140020441  test    eax, eax
0x140020443  js      short loc_140020457
0x140020445  mov     rcx, [rbp+ThreadHandle]; Handle
0x140020449  call    cs:__imp_ZwClose
0x140020450  nop     dword ptr [rax+rax+00h]
0x140020455  jmp     short loc_140020472
0x140020457  mov     rax, [rbx]
0x14002045a  lock dec dword ptr [rax+68h]
0x14002045e  mov     edx, 52505452h; Tag
0x140020463  mov     rcx, rbx; P
0x140020466  call    cs:__imp_ExFreePoolWithTag
0x14002046d  nop     dword ptr [rax+rax+00h]
0x140020472  mov     rcx, cs:WPP_GLOBAL_Control
0x140020479  lea     rax, WPP_GLOBAL_Control
0x140020480  cmp     rcx, rax
0x140020483  jz      short loc_1400204A4
0x140020485  mov     eax, [rcx+2Ch]
0x140020488  test    al, 1
0x14002048a  jz      short loc_1400204A4
0x14002048c  mov     rcx, [rcx+18h]
0x140020490  lea     r8, WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids
0x140020497  mov     edx, 10h
0x14002049c  mov     r9d, edi
0x14002049f  call    WPP_SF_d
0x1400204a4  lea     r11, [rsp+70h+var_s0]
0x1400204a9  mov     eax, edi
0x1400204ab  mov     rbx, [r11+18h]
0x1400204af  mov     rdi, [r11+20h]
0x1400204b3  mov     rsp, r11
0x1400204b6  pop     rbp
0x1400204b7  retn
```
