# CBcdUtils::AddEntryToBootDisplayOrder(_GUID const &)

- ea: `0x180007974`
- end: `0x180007b5a`
- name: `?AddEntryToBootDisplayOrder@CBcdUtils@@QEAAJAEBU_GUID@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(CBcdUtils *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000eb50`

## callees

- `0x180007974`
- `0x1800097ec`
- `0x18000aba4`
- `0x18001fd60`
- `0x18007ec9a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007a1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007a9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007a1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007a9a`
- `bcd!BcdCloseObject` at `0x180007b43`
- `bcd!BcdCloseObject` at `0x180007b43`
- `bcd!BcdOpenObject` at `0x1800079c5`
- `bcd!BcdOpenObject` at `0x1800079c5`
- `bcd!BcdGetElementData` at `0x1800079fb`
- `bcd!BcdGetElementData` at `0x180007a68`
- `bcd!BcdGetElementData` at `0x1800079fb`
- `bcd!BcdGetElementData` at `0x180007a68`
- `bcd!BcdSetElementData` at `0x180007af5`
- `bcd!BcdSetElementData` at `0x180007af5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBcdUtils::AddEntryToBootDisplayOrder(CBcdUtils *this, const struct _GUID *a2)
{
  _OWORD *v3; // rbx
  _OWORD *v4; // rdi
  __int64 v5; // rcx
  unsigned int v6; // esi
  int v7; // eax
  int ElementData; // eax
  _OWORD *v9; // rax
  signed int LastError; // eax
  int v11; // eax
  unsigned int v12; // esi
  unsigned int v13; // r15d
  _OWORD *v14; // rax
  unsigned int i; // ecx
  int v16; // eax
  int v17; // eax
  __int64 v19; // [rsp+28h] [rbp-8h]
  int v20; // [rsp+70h] [rbp+40h] BYREF
  SIZE_T uBytes; // [rsp+80h] [rbp+50h] BYREF
  __int64 v22; // [rsp+88h] [rbp+58h] BYREF

  LODWORD(uBytes) = 0;
  v22 = 0;
  v3 = 0;
  v4 = 0;
  v20 = 0;
  v5 = *((_QWORD *)this + 9);
  if ( !v5 )
  {
    v6 = -2147483638;
LABEL_17:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_18;
  }
  v7 = BcdOpenObject(v5, &GUID_WINDOWS_BOOTMGR, &v22);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v7, &v20) )
    goto LABEL_4;
  LODWORD(uBytes) = 0;
  ElementData = BcdGetElementData(v22, 603979777, 0, &uBytes, 0, 0);
  if ( ElementData != -1073741789 && !(unsigned int)SErrorConverter::C_NtStatus2HR(ElementData, &v20) )
    goto LABEL_4;
  v9 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v3 = v9;
  if ( !v9 )
    goto LABEL_8;
  v11 = BcdGetElementData(v22, 603979777, v9, &uBytes, v9, v19);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v11, &v20) )
  {
LABEL_4:
    v6 = v20;
    goto LABEL_17;
  }
  v12 = (unsigned int)uBytes >> 4;
  v13 = ((unsigned int)uBytes >> 4) + 1;
  v14 = LocalAlloc(0x40u, 16LL * v13);
  v4 = v14;
  if ( !v14 )
  {
LABEL_8:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    goto LABEL_17;
  }
  memset_0(v14, 0, 16LL * v13);
  for ( i = 0; i < v12; ++i )
    v4[i] = v3[i];
  v4[v12] = *a2;
  v16 = BcdSetElementData(v22, 603979777, v4, 16 * v13);
  v17 = SErrorConverter::C_NtStatus2HR(v16, &v20);
  v6 = v20;
  if ( !v17 )
    goto LABEL_17;
LABEL_18:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v4 )
    LocalFree(v4);
  if ( v3 )
    LocalFree(v3);
  if ( v22 )
    BcdCloseObject();
  return v6;
}

```

## disassembly

```asm
0x180007974  push    rbp
0x180007976  push    rbx
0x180007977  push    rsi
0x180007978  push    rdi
0x180007979  push    r12
0x18000797b  push    r14
0x18000797d  push    r15
0x18000797f  mov     rbp, rsp
0x180007982  sub     rsp, 30h
0x180007986  mov     r12, rdx
0x180007989  mov     dword ptr [rbp+uBytes], 0
0x180007990  mov     [rbp+arg_18], 0
0x180007998  xor     ebx, ebx
0x18000799a  mov     [rbp+var_10], rbx
0x18000799e  xor     edi, edi
0x1800079a0  mov     [rbp+var_8], rdi
0x1800079a4  mov     [rbp+arg_0], edi
0x1800079a7  mov     rcx, [rcx+48h]
0x1800079ab  test    rcx, rcx
0x1800079ae  jnz     short loc_1800079BA
0x1800079b0  mov     esi, 8000000Ah
0x1800079b5  jmp     loc_180007B0D
0x1800079ba  lea     r8, [rbp+arg_18]
0x1800079be  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1800079c5  call    cs:__imp_BcdOpenObject
0x1800079cb  mov     ecx, eax; int
0x1800079cd  lea     rdx, [rbp+arg_0]; int *
0x1800079d1  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x1800079d6  test    eax, eax
0x1800079d8  jnz     short loc_1800079E2
0x1800079da  mov     esi, [rbp+arg_0]
0x1800079dd  jmp     loc_180007B0D
0x1800079e2  mov     dword ptr [rbp+uBytes], 0
0x1800079e9  lea     r9, [rbp+uBytes]
0x1800079ed  xor     r8d, r8d
0x1800079f0  mov     esi, 24000001h
0x1800079f5  mov     edx, esi
0x1800079f7  mov     rcx, [rbp+arg_18]
0x1800079fb  call    cs:__imp_BcdGetElementData
0x180007a01  cmp     eax, 0C0000023h
0x180007a06  jz      short loc_180007A17
0x180007a08  lea     rdx, [rbp+arg_0]; int *
0x180007a0c  mov     ecx, eax; int
0x180007a0e  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180007a13  test    eax, eax
0x180007a15  jz      short loc_1800079DA
0x180007a17  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180007a1a  mov     ecx, 40h ; '@'; uFlags
0x180007a1f  call    cs:__imp_LocalAlloc
0x180007a25  mov     rbx, rax
0x180007a28  test    rax, rax
0x180007a2b  jnz     short loc_180007A57
0x180007a2d  call    cs:__imp_GetLastError
0x180007a33  test    eax, eax
0x180007a35  mov     esi, eax
0x180007a37  jnz     short loc_180007A43
0x180007a39  mov     esi, 80004005h
0x180007a3e  jmp     loc_180007B0D
0x180007a43  jle     loc_180007B0D
0x180007a49  movzx   esi, ax
0x180007a4c  or      esi, 80070000h
0x180007a52  jmp     loc_180007B0D
0x180007a57  mov     [rbp+var_10], rbx
0x180007a5b  lea     r9, [rbp+uBytes]
0x180007a5f  mov     r8, rbx
0x180007a62  mov     edx, esi
0x180007a64  mov     rcx, [rbp+arg_18]
0x180007a68  call    cs:__imp_BcdGetElementData
0x180007a6e  mov     ecx, eax; int
0x180007a70  lea     rdx, [rbp+arg_0]; int *
0x180007a74  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180007a79  test    eax, eax
0x180007a7b  jz      loc_1800079DA
0x180007a81  mov     esi, dword ptr [rbp+uBytes]
0x180007a84  shr     esi, 4
0x180007a87  lea     r15d, [rsi+1]
0x180007a8b  mov     r14d, r15d
0x180007a8e  shl     r14, 4
0x180007a92  mov     rdx, r14; uBytes
0x180007a95  mov     ecx, 40h ; '@'; uFlags
0x180007a9a  call    cs:__imp_LocalAlloc
0x180007aa0  mov     rdi, rax
0x180007aa3  test    rax, rax
0x180007aa6  jz      short loc_180007A2D
0x180007aa8  mov     [rbp+var_8], rdi
0x180007aac  mov     r8, r14; Size
0x180007aaf  xor     edx, edx; Val
0x180007ab1  mov     rcx, rdi; void *
0x180007ab4  call    memset_0
0x180007ab9  xor     ecx, ecx
0x180007abb  test    esi, esi
0x180007abd  jz      short loc_180007AD3
0x180007abf  mov     eax, ecx
0x180007ac1  add     rax, rax
0x180007ac4  movups  xmm0, xmmword ptr [rbx+rax*8]
0x180007ac8  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x180007acd  inc     ecx
0x180007acf  cmp     ecx, esi
0x180007ad1  jb      short loc_180007ABF
0x180007ad3  movups  xmm0, xmmword ptr [r12]
0x180007ad8  mov     eax, esi
0x180007ada  add     rax, rax
0x180007add  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x180007ae2  shl     r15d, 4
0x180007ae6  mov     r9d, r15d
0x180007ae9  mov     r8, rdi
0x180007aec  mov     edx, 24000001h
0x180007af1  mov     rcx, [rbp+arg_18]
0x180007af5  call    cs:__imp_BcdSetElementData
0x180007afb  mov     ecx, eax; int
0x180007afd  lea     rdx, [rbp+arg_0]; int *
0x180007b01  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180007b06  mov     esi, [rbp+arg_0]
0x180007b09  test    eax, eax
0x180007b0b  jnz     short loc_180007B14
0x180007b0d  mov     ecx, esi
0x180007b0f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180007b14  mov     ecx, esi
0x180007b16  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180007b1b  nop
0x180007b1c  test    rdi, rdi
0x180007b1f  jz      short loc_180007B2B
0x180007b21  mov     rcx, rdi; hMem
0x180007b24  call    cs:__imp_LocalFree
0x180007b2a  nop
0x180007b2b  test    rbx, rbx
0x180007b2e  jz      short loc_180007B3A
0x180007b30  mov     rcx, rbx; hMem
0x180007b33  call    cs:__imp_LocalFree
0x180007b39  nop
0x180007b3a  mov     rcx, [rbp+arg_18]
0x180007b3e  test    rcx, rcx
0x180007b41  jz      short loc_180007B49
0x180007b43  call    cs:__imp_BcdCloseObject
0x180007b49  mov     eax, esi
0x180007b4b  add     rsp, 30h
0x180007b4f  pop     r15
0x180007b51  pop     r14
0x180007b53  pop     r12
0x180007b55  pop     rdi
0x180007b56  pop     rsi
0x180007b57  pop     rbx
0x180007b58  pop     rbp
0x180007b59  retn
```
