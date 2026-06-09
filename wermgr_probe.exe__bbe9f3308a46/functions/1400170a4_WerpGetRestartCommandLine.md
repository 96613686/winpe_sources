# WerpGetRestartCommandLine

- ea: `0x1400170a4`
- end: `0x1400171a5`
- name: `WerpGetRestartCommandLine`
- size: `257`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140015604`

## callees

- `0x140002fbc`
- `0x140002fc8`
- `0x140003200`
- `0x140016b30`
- `0x1400170a4`
- `0x14001c930`
- `0x14001c9a8`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x140017177`
- `ntdll!DbgPrintEx` at `0x140017177`

## pseudocode

```c
signed int __fastcall WerpGetRestartCommandLine(void *a1, __int64 a2, _DWORD *a3, _DWORD *a4)
{
  signed int result; // eax
  __int64 v8; // rax
  DWORD CurrentProcessId_0; // eax
  _BYTE Src[2416]; // [rsp+30h] [rbp-1308h] BYREF
  _WORD Buffer[16]; // [rsp+9A0h] [rbp-998h] BYREF
  int v12; // [rsp+9C0h] [rbp-978h]
  int v13; // [rsp+9C4h] [rbp-974h]
  _WORD v14[1124]; // [rsp+A48h] [rbp-8F0h]

  memset_0(Src, 0, 0x968u);
  memcpy_0(Buffer, Src, 0x968u);
  if ( !a3 || *a3 )
  {
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Invalid arg\n", CurrentProcessId_0, 3523);
    return -2147024809;
  }
  else
  {
    result = WerpGetHeaderFromProcess(a1, Buffer);
    if ( result >= 0 )
    {
      if ( v13 )
      {
        if ( a4 )
          *a4 = v12;
        v8 = -1;
        do
          ++v8;
        while ( v14[v8] );
        *a3 = v8 + 1;
        return 0;
      }
      else
      {
        *a3 = 0;
        return -2147023728;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400170a4  mov     [rsp+arg_8], rbx
0x1400170a9  push    rbp
0x1400170aa  push    rsi
0x1400170ab  push    rdi
0x1400170ac  mov     eax, 1320h
0x1400170b1  call    _alloca_probe
0x1400170b6  sub     rsp, rax
0x1400170b9  mov     rax, cs:__security_cookie
0x1400170c0  xor     rax, rsp
0x1400170c3  mov     [rsp+1338h+var_28], rax
0x1400170cb  mov     rbx, r8
0x1400170ce  mov     rsi, rcx
0x1400170d1  mov     ebp, 968h
0x1400170d6  lea     rcx, [rsp+1338h+Src]; void *
0x1400170db  mov     r8d, ebp; Size
0x1400170de  xor     edx, edx; Val
0x1400170e0  mov     rdi, r9
0x1400170e3  call    memset_0
0x1400170e8  lea     rcx, [rsp+1338h+Buffer]; void *
0x1400170f0  mov     r8d, ebp; Size
0x1400170f3  lea     rdx, [rsp+1338h+Src]; Src
0x1400170f8  call    memcpy_0
0x1400170fd  xor     ebp, ebp
0x1400170ff  test    rbx, rbx
0x140017102  jz      short loc_140017159
0x140017104  cmp     [rbx], ebp
0x140017106  jnz     short loc_140017159
0x140017108  lea     rdx, [rsp+1338h+Buffer]; lpBuffer
0x140017110  mov     rcx, rsi; hProcess
0x140017113  call    WerpGetHeaderFromProcess
0x140017118  test    eax, eax
0x14001711a  js      short loc_140017182
0x14001711c  cmp     [rsp+1338h+var_974], ebp
0x140017123  jnz     short loc_14001712E
0x140017125  mov     [rbx], ebp
0x140017127  mov     eax, 80070490h
0x14001712c  jmp     short loc_140017182
0x14001712e  test    rdi, rdi
0x140017131  jz      short loc_14001713C
0x140017133  mov     eax, [rsp+1338h+var_978]
0x14001713a  mov     [rdi], eax
0x14001713c  lea     rcx, [rsp+1338h+var_8F0]
0x140017144  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017148  inc     rax
0x14001714b  cmp     [rcx+rax*2], bp
0x14001714f  jnz     short loc_140017148
0x140017151  inc     eax
0x140017153  mov     [rbx], eax
0x140017155  xor     eax, eax
0x140017157  jmp     short loc_140017182
0x140017159  call    GetCurrentProcessId_0
0x14001715e  mov     r9d, eax
0x140017161  mov     [rsp+1338h+var_1318], 0DC3h
0x140017169  lea     r8, aWerCrashapiUUE; "WER/CrashAPI/%u:%u: ERROR Invalid arg\n"
0x140017170  xor     edx, edx; Level
0x140017172  mov     ecx, 96h; ComponentId
0x140017177  call    cs:__imp_DbgPrintEx
0x14001717d  mov     eax, 80070057h
0x140017182  mov     rcx, [rsp+1338h+var_28]
0x14001718a  xor     rcx, rsp; StackCookie
0x14001718d  call    __security_check_cookie
0x140017192  mov     rbx, [rsp+1338h+arg_8]
0x14001719a  add     rsp, 1320h
0x1400171a1  pop     rdi
0x1400171a2  pop     rsi
0x1400171a3  pop     rbp
0x1400171a4  retn
```
