# WdcHandleMonitor::UpdateInitialize(void)

- ea: `0x180038e30`
- end: `0x180038ee1`
- name: `?UpdateInitialize@WdcHandleMonitor@@MEAAJXZ`
- size: `177`
- prototype: `__int64 __fastcall(WdcHandleMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000b854`
- `0x180038e30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180038e6a`
- `KERNEL32!GetLastError` at `0x180038e8d`
- `KERNEL32!GetLastError` at `0x180038e6a`
- `KERNEL32!GetLastError` at `0x180038e8d`
- `KERNEL32!CreateEventW` at `0x180038e57`
- `KERNEL32!CreateEventW` at `0x180038e57`

## string_xrefs

- `0x180038ebc`: `WdcHandleMonitor::UpdateInitialize`

## pseudocode

```c
__int64 __fastcall WdcHandleMonitor::UpdateInitialize(WdcHandleMonitor *this)
{
  __int64 i; // rbx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v5; // sf
  bool v6; // sf
  signed int v8; // [rsp+20h] [rbp-18h]

  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + i + 1171) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v5 = LastError < 0;
      if ( !LastError )
        goto LABEL_14;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v5 = LastError < 0;
      }
      if ( v5 )
        goto LABEL_15;
    }
    if ( *((_QWORD *)this + i + 1171) == -1 )
    {
      LastError = GetLastError();
      v6 = LastError < 0;
      if ( !LastError )
      {
LABEL_14:
        LastError = -2147467259;
LABEL_15:
        v8 = LastError;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\handle.cpp",
          "WdcHandleMonitor::UpdateInitialize",
          0,
          L"FAILURE: 0x%08x",
          v8);
        return 0;
      }
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v6 = LastError < 0;
      }
      if ( v6 )
        goto LABEL_15;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180038e30  mov     [rsp+arg_0], rbx
0x180038e35  mov     [rsp+arg_8], rsi
0x180038e3a  push    rdi
0x180038e3b  sub     rsp, 30h
0x180038e3f  mov     rdi, rcx
0x180038e42  xor     ebx, ebx
0x180038e44  cmp     ebx, 3
0x180038e47  jnb     loc_180038ECF
0x180038e4d  xor     r9d, r9d; lpName
0x180038e50  xor     r8d, r8d; bInitialState
0x180038e53  xor     edx, edx; bManualReset
0x180038e55  xor     ecx, ecx; lpEventAttributes
0x180038e57  call    cs:__imp_CreateEventW
0x180038e5d  mov     [rdi+rbx*8+2498h], rax
0x180038e65  test    rax, rax
0x180038e68  jnz     short loc_180038E82
0x180038e6a  call    cs:__imp_GetLastError
0x180038e70  test    eax, eax
0x180038e72  jz      short loc_180038EA9
0x180038e74  jle     short loc_180038E80
0x180038e76  movzx   eax, ax
0x180038e79  or      eax, 80070000h
0x180038e7e  test    eax, eax
0x180038e80  js      short loc_180038EAE
0x180038e82  cmp     qword ptr [rdi+rbx*8+2498h], 0FFFFFFFFFFFFFFFFh
0x180038e8b  jnz     short loc_180038EA5
0x180038e8d  call    cs:__imp_GetLastError
0x180038e93  test    eax, eax
0x180038e95  jz      short loc_180038EA9
0x180038e97  jle     short loc_180038EA3
0x180038e99  movzx   eax, ax
0x180038e9c  or      eax, 80070000h
0x180038ea1  test    eax, eax
0x180038ea3  js      short loc_180038EAE
0x180038ea5  inc     ebx
0x180038ea7  jmp     short loc_180038E44
0x180038ea9  mov     eax, 80004005h
0x180038eae  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180038eb5  mov     [rsp+38h+var_18], eax
0x180038eb9  xor     r8d, r8d; int
0x180038ebc  lea     rdx, aWdchandlemonit; "WdcHandleMonitor::UpdateInitialize"
0x180038ec3  lea     rcx, aBaseDiagnosisP_33; "base\\diagnosis\\pdui\\perfmon\\mon\\ha"...
0x180038eca  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180038ecf  mov     rbx, [rsp+38h+arg_0]
0x180038ed4  xor     eax, eax
0x180038ed6  mov     rsi, [rsp+38h+arg_8]
0x180038edb  add     rsp, 30h
0x180038edf  pop     rdi
0x180038ee0  retn
```
