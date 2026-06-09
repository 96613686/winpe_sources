# CWdsTransportContentProvider::get_FilePath(ushort * *)

- ea: `0x180018990`
- end: `0x180018a0d`
- name: `?get_FilePath@CWdsTransportContentProvider@@UEAAJPEAPEAG@Z`
- size: `125`
- prototype: `__int64 __fastcall(CWdsTransportContentProvider *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180018990`
- `0x180018b34`

## import_xrefs

- `WdsCommonLib!?SysAllocStringHr@@YAJPEBGPEAPEAG@Z` at `0x1800189d5`
- `WdsCommonLib!?SysAllocStringHr@@YAJPEBGPEAPEAG@Z` at `0x1800189d5`

## pseudocode

```c
__int64 __fastcall CWdsTransportContentProvider::get_FilePath(const unsigned __int16 **this, unsigned __int16 **a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v10, this + 8);
  if ( a2 || (v6 = -2147024809, (int)ElValidateHr_13(2147942487LL, v4, v5, 239) >= 0) )
  {
    v6 = SysAllocStringHr(this[15], a2);
    ElValidateHr_13(v6, v7, v8, 243);
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return v6;
}

```

## disassembly

```asm
0x180018990  mov     [rsp+arg_0], rbx
0x180018995  mov     [rsp+arg_8], rsi
0x18001899a  push    rdi
0x18001899b  sub     rsp, 30h
0x18001899f  mov     rdi, rdx
0x1800189a2  mov     rsi, rcx
0x1800189a5  lea     rdx, [rcx+40h]
0x1800189a9  lea     rcx, [rsp+38h+var_18]
0x1800189ae  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x1800189b3  test    rdi, rdi
0x1800189b6  jnz     short loc_1800189CE
0x1800189b8  mov     ebx, 80070057h
0x1800189bd  mov     r9d, 0EFh
0x1800189c3  mov     ecx, ebx
0x1800189c5  call    ElValidateHr_13
0x1800189ca  test    eax, eax
0x1800189cc  js      short loc_1800189F0
0x1800189ce  mov     rcx, [rsi+78h]
0x1800189d2  mov     rdx, rdi
0x1800189d5  call    cs:__imp_?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x1800189dc  nop     dword ptr [rax+rax+00h]
0x1800189e1  mov     ecx, eax
0x1800189e3  mov     r9d, 0F3h
0x1800189e9  mov     ebx, eax
0x1800189eb  call    ElValidateHr_13
0x1800189f0  lea     rcx, [rsp+38h+var_18]
0x1800189f5  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x1800189fa  mov     rsi, [rsp+38h+arg_8]
0x1800189ff  mov     eax, ebx
0x180018a01  mov     rbx, [rsp+38h+arg_0]
0x180018a06  add     rsp, 30h
0x180018a0a  pop     rdi
0x180018a0b  retn
```
