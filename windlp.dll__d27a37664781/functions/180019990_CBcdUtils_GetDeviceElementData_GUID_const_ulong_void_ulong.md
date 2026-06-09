# CBcdUtils::GetDeviceElementData(_GUID const &,ulong,void * *,ulong *)

- ea: `0x180019990`
- end: `0x180019afa`
- name: `?GetDeviceElementData@CBcdUtils@@QEAAJAEBU_GUID@@KPEAPEAXPEAK@Z`
- size: `362`
- prototype: `__int64 __fastcall(CBcdUtils *__hidden this, const struct _GUID *, unsigned int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002b240`

## callees

- `0x1800097ec`
- `0x18000aba4`
- `0x180019990`
- `0x18001fd60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019acf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019acf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019a4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019a4b`
- `bcd!BcdCloseObject` at `0x180019adf`
- `bcd!BcdCloseObject` at `0x180019adf`
- `bcd!BcdOpenObject` at `0x1800199f6`
- `bcd!BcdOpenObject` at `0x1800199f6`
- `bcd!BcdGetElementData` at `0x180019a27`
- `bcd!BcdGetElementData` at `0x180019a99`
- `bcd!BcdGetElementData` at `0x180019a27`
- `bcd!BcdGetElementData` at `0x180019a99`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBcdUtils::GetDeviceElementData(
        CBcdUtils *this,
        const struct _GUID *a2,
        __int64 a3,
        void **a4,
        unsigned int *a5)
{
  void *v6; // rbx
  __int64 v7; // rcx
  unsigned int v8; // edi
  unsigned int *v9; // rsi
  __int64 v10; // rcx
  int v11; // eax
  int ElementData; // eax
  HLOCAL v13; // rax
  void *v14; // rdi
  signed int LastError; // eax
  int v16; // eax
  __int64 v17; // rdx
  SIZE_T uBytes; // [rsp+20h] [rbp-20h] BYREF
  __int64 v20; // [rsp+28h] [rbp-18h] BYREF
  HLOCAL v21; // [rsp+30h] [rbp-10h]
  int v22; // [rsp+70h] [rbp+30h] BYREF

  v20 = 0;
  v6 = 0;
  v21 = 0;
  LODWORD(uBytes) = 0;
  v22 = 0;
  if ( !a4 || (v9 = a5) == 0 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_19;
  }
  v10 = *((_QWORD *)this + 9);
  if ( !v10 )
  {
    v8 = -2147483638;
LABEL_7:
    v7 = v8;
    goto LABEL_3;
  }
  v11 = BcdOpenObject(v10, a2, &v20);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v11, &v22) )
    goto LABEL_9;
  LODWORD(uBytes) = 0;
  ElementData = BcdGetElementData(v20, 285212673, 0, &uBytes);
  if ( ElementData != -1073741789 && !(unsigned int)SErrorConverter::C_NtStatus2HR(ElementData, &v22) )
    goto LABEL_9;
  v13 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v14 = v13;
  if ( !v13 )
  {
    v6 = 0;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    goto LABEL_7;
  }
  v6 = v13;
  v21 = v13;
  v16 = BcdGetElementData(v20, 285212673, v13, &uBytes);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v16, &v22) )
  {
LABEL_9:
    v8 = v22;
    goto LABEL_7;
  }
  v6 = 0;
  *a4 = v14;
  *v9 = uBytes;
  v8 = v22;
LABEL_19:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( v6 )
    LocalFree(v6);
  if ( v20 )
    BcdCloseObject(v20, v17);
  return v8;
}

```

## disassembly

```asm
0x180019990  mov     [rsp-18h+arg_0], rbx
0x180019995  mov     [rsp-18h+arg_8], rsi
0x18001999a  mov     [rsp-18h+arg_10], r8d
0x18001999f  push    rbp
0x1800199a0  push    rdi
0x1800199a1  push    r14
0x1800199a3  mov     rbp, rsp
0x1800199a6  sub     rsp, 40h
0x1800199aa  mov     r14, r9
0x1800199ad  mov     [rbp+var_18], 0
0x1800199b5  xor     ebx, ebx
0x1800199b7  mov     [rbp+var_10], rbx
0x1800199bb  mov     dword ptr [rbp+uBytes], ebx
0x1800199be  mov     [rbp+arg_10], ebx
0x1800199c1  test    r9, r9
0x1800199c4  jnz     short loc_1800199D7
0x1800199c6  mov     ecx, 80070057h
0x1800199cb  mov     edi, ecx
0x1800199cd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800199d2  jmp     loc_180019ABF
0x1800199d7  mov     rsi, [rbp+arg_20]
0x1800199db  test    rsi, rsi
0x1800199de  jz      short loc_1800199C6
0x1800199e0  mov     rcx, [rcx+48h]
0x1800199e4  test    rcx, rcx
0x1800199e7  jnz     short loc_1800199F2
0x1800199e9  mov     edi, 8000000Ah
0x1800199ee  mov     ecx, edi
0x1800199f0  jmp     short loc_1800199CD
0x1800199f2  lea     r8, [rbp+var_18]
0x1800199f6  call    cs:__imp_BcdOpenObject
0x1800199fc  mov     ecx, eax; int
0x1800199fe  lea     rdx, [rbp+arg_10]; int *
0x180019a02  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180019a07  test    eax, eax
0x180019a09  jnz     short loc_180019A10
0x180019a0b  mov     edi, [rbp+arg_10]
0x180019a0e  jmp     short loc_1800199EE
0x180019a10  mov     dword ptr [rbp+uBytes], 0
0x180019a17  lea     r9, [rbp+uBytes]
0x180019a1b  xor     r8d, r8d
0x180019a1e  mov     edx, 11000001h
0x180019a23  mov     rcx, [rbp+var_18]
0x180019a27  call    cs:__imp_BcdGetElementData
0x180019a2d  cmp     eax, 0C0000023h
0x180019a32  jz      short loc_180019A43
0x180019a34  lea     rdx, [rbp+arg_10]; int *
0x180019a38  mov     ecx, eax; int
0x180019a3a  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180019a3f  test    eax, eax
0x180019a41  jz      short loc_180019A0B
0x180019a43  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180019a46  mov     ecx, 40h ; '@'; uFlags
0x180019a4b  call    cs:__imp_LocalAlloc
0x180019a51  mov     rdi, rax
0x180019a54  test    rax, rax
0x180019a57  jnz     short loc_180019A82
0x180019a59  xor     ebx, ebx
0x180019a5b  call    cs:__imp_GetLastError
0x180019a61  mov     edi, eax
0x180019a63  test    eax, eax
0x180019a65  jnz     short loc_180019A6E
0x180019a67  mov     edi, 80004005h
0x180019a6c  jmp     short loc_1800199EE
0x180019a6e  jle     loc_1800199EE
0x180019a74  movzx   edi, ax
0x180019a77  or      edi, 80070000h
0x180019a7d  jmp     loc_1800199EE
0x180019a82  mov     rbx, rdi
0x180019a85  mov     [rbp+var_10], rbx
0x180019a89  lea     r9, [rbp+uBytes]
0x180019a8d  mov     r8, rdi
0x180019a90  mov     edx, 11000001h
0x180019a95  mov     rcx, [rbp+var_18]
0x180019a99  call    cs:__imp_BcdGetElementData
0x180019a9f  mov     ecx, eax; int
0x180019aa1  lea     rdx, [rbp+arg_10]; int *
0x180019aa5  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180019aaa  test    eax, eax
0x180019aac  jz      loc_180019A0B
0x180019ab2  xor     ebx, ebx
0x180019ab4  mov     [r14], rdi
0x180019ab7  mov     eax, dword ptr [rbp+uBytes]
0x180019aba  mov     [rsi], eax
0x180019abc  mov     edi, [rbp+arg_10]
0x180019abf  mov     ecx, edi
0x180019ac1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180019ac6  nop
0x180019ac7  test    rbx, rbx
0x180019aca  jz      short loc_180019AD6
0x180019acc  mov     rcx, rbx; hMem
0x180019acf  call    cs:__imp_LocalFree
0x180019ad5  nop
0x180019ad6  mov     rcx, [rbp+var_18]
0x180019ada  test    rcx, rcx
0x180019add  jz      short loc_180019AE5
0x180019adf  call    cs:__imp_BcdCloseObject
0x180019ae5  mov     eax, edi
0x180019ae7  mov     rbx, [rsp+40h+arg_0]
0x180019aec  mov     rsi, [rsp+40h+arg_8]
0x180019af1  add     rsp, 40h
0x180019af5  pop     r14
0x180019af7  pop     rdi
0x180019af8  pop     rbp
0x180019af9  retn
```
