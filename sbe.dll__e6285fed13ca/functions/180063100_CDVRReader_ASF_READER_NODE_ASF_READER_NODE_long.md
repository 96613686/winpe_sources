# CDVRReader::ASF_READER_NODE::ASF_READER_NODE(long *)

- ea: `0x180063100`
- end: `0x18006321e`
- name: `??0ASF_READER_NODE@CDVRReader@@QEAA@PEAJ@Z`
- size: `286`
- prototype: `__int64 __fastcall(CDVRReader::ASF_READER_NODE *__hidden this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180066fc4`

## callees

- `0x18005faec`
- `0x180063100`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18006316f`
- `KERNEL32!CreateEventW` at `0x1800631aa`
- `KERNEL32!CreateEventW` at `0x18006316f`
- `KERNEL32!CreateEventW` at `0x1800631aa`
- `KERNEL32!GetLastError` at `0x18006317e`
- `KERNEL32!GetLastError` at `0x1800631b9`
- `KERNEL32!GetLastError` at `0x18006317e`
- `KERNEL32!GetLastError` at `0x1800631b9`
- `WMVCore!WMCreateSyncReader` at `0x1800631d9`
- `WMVCore!WMCreateSyncReader` at `0x1800631d9`

## pseudocode

```c
CDVRReader::ASF_READER_NODE *__fastcall CDVRReader::ASF_READER_NODE::ASF_READER_NODE(
        CDVRReader::ASF_READER_NODE *this,
        int *a2)
{
  HANDLE EventW; // rax
  signed int v5; // eax
  HANDLE v6; // rax
  signed int LastError; // eax
  HRESULT v9; // [rsp+20h] [rbp-18h]

  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 18) = -2147467259;
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 7) = EventW;
  if ( EventW )
  {
    v6 = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)this + 8) = v6;
    if ( v6 )
    {
      v9 = WMCreateSyncReader(0, 0, (IWMSyncReader **)this + 2);
      if ( v9 >= 0 )
        v9 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v9 = LastError;
    }
  }
  else
  {
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v9 = v5;
    *((_QWORD *)this + 8) = 0;
  }
  if ( a2 )
    *a2 = v9;
  return this;
}

```

## disassembly

```asm
0x180063100  mov     rax, rsp
0x180063103  mov     [rax+18h], rsi
0x180063107  mov     [rax+20h], rdi
0x18006310b  mov     [rax+10h], rdx
0x18006310f  mov     [rax+8], rcx
0x180063113  push    r14
0x180063115  sub     rsp, 30h
0x180063119  mov     rsi, rdx
0x18006311c  mov     rdi, rcx
0x18006311f  mov     qword ptr [rcx+10h], 0
0x180063127  mov     qword ptr [rcx+18h], 0
0x18006312f  mov     qword ptr [rcx+20h], 0
0x180063137  mov     qword ptr [rcx+28h], 0
0x18006313f  mov     dword ptr [rcx+30h], 0
0x180063146  mov     dword ptr [rcx+48h], 80004005h
0x18006314d  mov     dword ptr [rax-18h], 0
0x180063154  mov     qword ptr [rcx+8], 0
0x18006315c  mov     qword ptr [rcx], 0
0x180063163  xor     r9d, r9d; lpName
0x180063166  xor     r8d, r8d; bInitialState
0x180063169  lea     edx, [r9+1]; bManualReset
0x18006316d  xor     ecx, ecx; lpEventAttributes
0x18006316f  call    cs:__imp_CreateEventW
0x180063175  mov     [rdi+38h], rax
0x180063179  test    rax, rax
0x18006317c  jnz     short loc_18006319E
0x18006317e  call    cs:__imp_GetLastError
0x180063184  test    eax, eax
0x180063186  jle     short loc_180063190
0x180063188  movzx   eax, ax
0x18006318b  or      eax, 80070000h
0x180063190  mov     [rsp+38h+var_18], eax
0x180063194  mov     qword ptr [rdi+40h], 0
0x18006319c  jmp     short loc_1800631F3
0x18006319e  xor     r9d, r9d; lpName
0x1800631a1  lea     edx, [r9+1]; bManualReset
0x1800631a5  xor     ecx, ecx; lpEventAttributes
0x1800631a7  mov     r8d, edx; bInitialState
0x1800631aa  call    cs:__imp_CreateEventW
0x1800631b0  mov     [rdi+40h], rax
0x1800631b4  test    rax, rax
0x1800631b7  jnz     short loc_1800631D1
0x1800631b9  call    cs:__imp_GetLastError
0x1800631bf  test    eax, eax
0x1800631c1  jle     short loc_1800631CB
0x1800631c3  movzx   eax, ax
0x1800631c6  or      eax, 80070000h
0x1800631cb  mov     [rsp+38h+var_18], eax
0x1800631cf  jmp     short loc_1800631F3
0x1800631d1  lea     r8, [rdi+10h]; ppSyncReader
0x1800631d5  xor     edx, edx; dwRights
0x1800631d7  xor     ecx, ecx; pUnkCert
0x1800631d9  call    cs:__imp_WMCreateSyncReader
0x1800631df  mov     [rsp+38h+var_18], eax
0x1800631e3  mov     eax, [rsp+38h+var_18]
0x1800631e7  test    eax, eax
0x1800631e9  js      short loc_1800631F3
0x1800631eb  mov     [rsp+38h+var_18], 0
0x1800631f3  jmp     short loc_1800631FF
0x1800631f5  mov     rdi, [rsp+38h+arg_0]
0x1800631fa  mov     rsi, [rsp+38h+arg_8]
0x1800631ff  test    rsi, rsi
0x180063202  jz      short loc_18006320A
0x180063204  mov     eax, [rsp+38h+var_18]
0x180063208  mov     [rsi], eax
0x18006320a  mov     rax, rdi
0x18006320d  mov     rsi, [rsp+38h+arg_10]
0x180063212  mov     rdi, [rsp+38h+arg_18]
0x180063217  add     rsp, 30h
0x18006321b  pop     r14
0x18006321d  retn
0x1800b35a6  push    rbp
0x1800b35a8  sub     rsp, 20h
0x1800b35ac  mov     rbp, rdx
0x1800b35af  lea     rdx, [rbp+20h]; int *
0x1800b35b3  call    ?SBE_DelayLoadDllExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@PEAJ@Z; SBE_DelayLoadDllExceptionFilter(_EXCEPTION_POINTERS *,long *)
0x1800b35b8  nop
0x1800b35b9  add     rsp, 20h
0x1800b35bd  pop     rbp
0x1800b35be  retn
0x1800b35c0  push    rbp
0x1800b35c2  sub     rsp, 20h
0x1800b35c6  mov     rbp, rdx
0x1800b35c9  mov     rcx, [rbp+48h]
0x1800b35cd  test    rcx, rcx
0x1800b35d0  jz      short loc_1800B35D7
0x1800b35d2  mov     eax, [rbp+20h]
0x1800b35d5  mov     [rcx], eax
0x1800b35d7  add     rsp, 20h
0x1800b35db  pop     rbp
0x1800b35dc  retn
```
