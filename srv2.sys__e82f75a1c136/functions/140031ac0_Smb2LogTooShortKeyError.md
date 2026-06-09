# Smb2LogTooShortKeyError

- ea: `0x140031ac0`
- end: `0x140031c1c`
- name: `Smb2LogTooShortKeyError`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140095748`

## callees

- `0x140031740`
- `0x140031ac0`
- `0x140031c24`

## import_xrefs

- `ksecdd!FreeContextBuffer` at `0x140031bec`
- `ksecdd!FreeContextBuffer` at `0x140031c02`
- `ksecdd!FreeContextBuffer` at `0x140031bec`
- `ksecdd!FreeContextBuffer` at `0x140031c02`
- `ksecdd!MapSecurityError` at `0x140031b00`
- `ksecdd!MapSecurityError` at `0x140031b3d`
- `ksecdd!MapSecurityError` at `0x140031b00`
- `ksecdd!MapSecurityError` at `0x140031b3d`
- `ksecdd!QueryContextAttributesW` at `0x140031af2`
- `ksecdd!QueryContextAttributesW` at `0x140031b2f`
- `ksecdd!QueryContextAttributesW` at `0x140031af2`
- `ksecdd!QueryContextAttributesW` at `0x140031b2f`

## pseudocode

```c
int __fastcall Smb2LogTooShortKeyError(__int64 a1, _QWORD *a2, struct _SecHandle *a3, _DWORD *a4)
{
  __int64 *v5; // rdi
  __int16 v6; // bx
  SECURITY_STATUS ContextAttributesW; // eax
  SECURITY_STATUS v11; // eax
  NTSTATUS v12; // eax
  int v13; // r8d
  int v14; // r9d
  PVOID v15; // rcx
  int v16; // edx
  PDEVICE_OBJECT *v17; // rax
  int v19; // [rsp+30h] [rbp-68h]
  PVOID pvContextBuffer; // [rsp+50h] [rbp-48h] BYREF
  PVOID pBuffer[8]; // [rsp+58h] [rbp-40h] BYREF

  v5 = &qword_140041C50;
  LOBYTE(v6) = 0;
  pBuffer[0] = 0;
  ContextAttributesW = QueryContextAttributesW(a3, 0xAu, pBuffer);
  if ( MapSecurityError(ContextAttributesW) >= 0 )
    v6 = *((_WORD *)pBuffer[0] + 3);
  pvContextBuffer = 0;
  v11 = QueryContextAttributesW(a3, 1u, &pvContextBuffer);
  v12 = MapSecurityError(v11);
  v15 = pvContextBuffer;
  if ( v12 >= 0 )
    v5 = (__int64 *)pvContextBuffer;
  v16 = (int)WPP_GLOBAL_Control;
  v17 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    LODWORD(v17) = WPP_SF_DDidS(
                     WPP_GLOBAL_Control->AttachedDevice,
                     (_DWORD)WPP_GLOBAL_Control,
                     v13,
                     v14,
                     *a4,
                     *a2,
                     v6,
                     (__int64)v5);
    v15 = pvContextBuffer;
  }
  if ( (byte_14004C33A & 1) != 0 )
  {
    LODWORD(v17) = McTemplateK0hzr0qqxzq_EtwWriteTransfer(
                     *(_QWORD *)(a1 + 96),
                     v16,
                     v13,
                     *(_WORD *)(*(_QWORD *)(a1 + 96) + 360LL) >> 1,
                     *(_QWORD *)(*(_QWORD *)(a1 + 96) + 368LL),
                     *a4,
                     v19,
                     *a2,
                     (__int64)v5,
                     v6);
    v15 = pvContextBuffer;
  }
  if ( v15 )
    LODWORD(v17) = FreeContextBuffer(v15);
  if ( pBuffer[0] )
    LODWORD(v17) = FreeContextBuffer(pBuffer[0]);
  return (int)v17;
}

```

## disassembly

```asm
0x140031ac0  push    rbx
0x140031ac2  push    rbp
0x140031ac3  push    rsi
0x140031ac4  push    rdi
0x140031ac5  push    r14
0x140031ac7  push    r15
0x140031ac9  sub     rsp, 68h
0x140031acd  mov     rbp, r8
0x140031ad0  lea     rdi, qword_140041C50
0x140031ad7  xor     ebx, ebx
0x140031ad9  lea     r8, [rsp+98h+pBuffer]; pBuffer
0x140031ade  mov     r14, rdx
0x140031ae1  mov     [rsp+98h+pBuffer], rbx
0x140031ae6  mov     r15, rcx
0x140031ae9  mov     rsi, r9
0x140031aec  mov     rcx, rbp; phContext
0x140031aef  lea     edx, [rbx+0Ah]; ulAttribute
0x140031af2  call    cs:__imp_QueryContextAttributesW
0x140031af9  nop     dword ptr [rax+rax+00h]
0x140031afe  mov     ecx, eax; SecStatus
0x140031b00  call    cs:__imp_MapSecurityError
0x140031b07  nop     dword ptr [rax+rax+00h]
0x140031b0c  test    eax, eax
0x140031b0e  js      short loc_140031B19
0x140031b10  mov     rax, [rsp+98h+pBuffer]
0x140031b15  movzx   ebx, word ptr [rax+6]
0x140031b19  lea     r8, [rsp+98h+pvContextBuffer]; pBuffer
0x140031b1e  mov     [rsp+98h+pvContextBuffer], 0
0x140031b27  mov     edx, 1; ulAttribute
0x140031b2c  mov     rcx, rbp; phContext
0x140031b2f  call    cs:__imp_QueryContextAttributesW
0x140031b36  nop     dword ptr [rax+rax+00h]
0x140031b3b  mov     ecx, eax; SecStatus
0x140031b3d  call    cs:__imp_MapSecurityError
0x140031b44  nop     dword ptr [rax+rax+00h]
0x140031b49  mov     rcx, [rsp+98h+pvContextBuffer]
0x140031b4e  test    eax, eax
0x140031b50  cmovns  rdi, rcx
0x140031b54  mov     rdx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140031b5b  lea     rax, WPP_GLOBAL_Control
0x140031b62  cmp     rdx, rax
0x140031b65  jz      short loc_140031B9E
0x140031b67  test    dword ptr [rdx+2Ch], 20000h
0x140031b6e  jz      short loc_140031B9E
0x140031b70  cmp     byte ptr [rdx+29h], 1
0x140031b74  jb      short loc_140031B9E
0x140031b76  mov     rcx, [rdx+18h]
0x140031b7a  mov     [rsp+98h+var_60], rdi
0x140031b7f  movzx   eax, bx
0x140031b82  mov     [rsp+98h+var_68], eax
0x140031b86  mov     rax, [r14]
0x140031b89  mov     [rsp+98h+var_70], rax
0x140031b8e  mov     eax, [rsi]
0x140031b90  mov     dword ptr [rsp+98h+var_78], eax
0x140031b94  call    WPP_SF_DDidS
0x140031b99  mov     rcx, [rsp+98h+pvContextBuffer]
0x140031b9e  test    cs:byte_14004C33A, 1
0x140031ba5  jz      short loc_140031BE7
0x140031ba7  mov     rcx, [r15+60h]
0x140031bab  movzx   eax, bx
0x140031bae  mov     [rsp+98h+var_50], eax
0x140031bb2  mov     rax, [r14]
0x140031bb5  movzx   r9d, word ptr [rcx+168h]
0x140031bbd  mov     [rsp+98h+var_58], rdi
0x140031bc2  mov     [rsp+98h+var_60], rax
0x140031bc7  mov     eax, [rsi]
0x140031bc9  mov     dword ptr [rsp+98h+var_70], eax
0x140031bcd  mov     rax, [rcx+170h]
0x140031bd4  shr     r9w, 1
0x140031bd8  mov     [rsp+98h+var_78], rax
0x140031bdd  call    McTemplateK0hzr0qqxzq_EtwWriteTransfer
0x140031be2  mov     rcx, [rsp+98h+pvContextBuffer]; pvContextBuffer
0x140031be7  test    rcx, rcx
0x140031bea  jz      short loc_140031BF8
0x140031bec  call    cs:__imp_FreeContextBuffer
0x140031bf3  nop     dword ptr [rax+rax+00h]
0x140031bf8  mov     rcx, [rsp+98h+pBuffer]; pvContextBuffer
0x140031bfd  test    rcx, rcx
0x140031c00  jz      short loc_140031C0E
0x140031c02  call    cs:__imp_FreeContextBuffer
0x140031c09  nop     dword ptr [rax+rax+00h]
0x140031c0e  add     rsp, 68h
0x140031c12  pop     r15
0x140031c14  pop     r14
0x140031c16  pop     rdi
0x140031c17  pop     rsi
0x140031c18  pop     rbp
0x140031c19  pop     rbx
0x140031c1a  retn
```
