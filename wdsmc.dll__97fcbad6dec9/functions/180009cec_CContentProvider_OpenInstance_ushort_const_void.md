# CContentProvider::OpenInstance(ushort const *,void * *)

- ea: `0x180009cec`
- end: `0x180009dbf`
- name: `?OpenInstance@CContentProvider@@QEAAKPEBGPEAPEAX@Z`
- size: `211`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002368`

## callees

- `0x180009cec`
- `0x180024dec`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009d1d`
- `KERNEL32!LeaveCriticalSection` at `0x180009d2c`
- `KERNEL32!LeaveCriticalSection` at `0x180009d1d`
- `KERNEL32!LeaveCriticalSection` at `0x180009d2c`
- `KERNEL32!EnterCriticalSection` at `0x180009d09`
- `KERNEL32!EnterCriticalSection` at `0x180009d09`

## pseudocode

```c
__int64 __fastcall CContentProvider::OpenInstance(
        LPCRITICAL_SECTION lpCriticalSection,
        const unsigned __int16 *a2,
        void **a3)
{
  unsigned int v6; // ebx
  __int64 (__fastcall *OwningThread)(const unsigned __int16 *, void **); // rbx
  int v8; // eax
  const char *v9; // rdx

  EnterCriticalSection(lpCriticalSection);
  if ( lpCriticalSection[1].LockCount )
  {
    OwningThread = (__int64 (__fastcall *)(const unsigned __int16 *, void **))lpCriticalSection[2].OwningThread;
    LeaveCriticalSection(lpCriticalSection);
    v8 = OwningThread(a2, a3);
    v6 = v8;
    if ( v8 < 0 && (v8 & 0x1FFF0000) == 0x70000 )
      v6 = (unsigned __int16)v8;
    if ( ElValidateWin32(v6, v9, "base\\eco\\wds\\transport\\server\\mc\\contentprovider.cpp", 0x21Au) )
      CEventLog::Log((CEventLog *)&hEventLog, 0xC1210257, 3);
  }
  else
  {
    v6 = 21;
    LeaveCriticalSection(lpCriticalSection);
  }
  return v6;
}

```

## disassembly

```asm
0x180009cec  mov     [rsp+arg_0], rbx
0x180009cf1  mov     [rsp+arg_8], rbp
0x180009cf6  mov     [rsp+arg_10], rsi
0x180009cfb  push    rdi
0x180009cfc  sub     rsp, 50h
0x180009d00  mov     rbp, r8
0x180009d03  mov     rsi, rdx
0x180009d06  mov     rdi, rcx
0x180009d09  call    cs:__imp_EnterCriticalSection
0x180009d0f  cmp     dword ptr [rdi+30h], 0
0x180009d13  mov     rcx, rdi; lpCriticalSection
0x180009d16  jnz     short loc_180009D28
0x180009d18  mov     ebx, 15h
0x180009d1d  call    cs:__imp_LeaveCriticalSection
0x180009d23  jmp     loc_180009DA8
0x180009d28  mov     rbx, [rdi+60h]
0x180009d2c  call    cs:__imp_LeaveCriticalSection
0x180009d32  mov     rdx, rbp
0x180009d35  mov     rcx, rsi
0x180009d38  mov     rax, rbx
0x180009d3b  call    cs:__guard_dispatch_icall_fptr
0x180009d41  mov     ebx, eax
0x180009d43  test    eax, eax
0x180009d45  jns     short loc_180009D56
0x180009d47  and     eax, 1FFF0000h
0x180009d4c  cmp     eax, 70000h
0x180009d51  jnz     short loc_180009D56
0x180009d53  movzx   ebx, bx
0x180009d56  mov     r9d, 21Ah; unsigned int
0x180009d5c  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180009d63  mov     ecx, ebx; unsigned int
0x180009d65  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009d6a  test    eax, eax
0x180009d6c  jz      short loc_180009DA8
0x180009d6e  mov     rcx, [rdi+28h]
0x180009d72  mov     r9d, 1
0x180009d78  mov     [rsp+58h+var_18], ebx
0x180009d7c  mov     edx, 0C1210257h; unsigned int
0x180009d81  mov     [rsp+58h+var_20], 5
0x180009d89  mov     [rsp+58h+var_28], rsi
0x180009d8e  mov     [rsp+58h+var_30], r9d
0x180009d93  lea     r8d, [r9+2]; int
0x180009d97  mov     [rsp+58h+var_38], rcx
0x180009d9c  lea     rcx, hEventLog; this
0x180009da3  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180009da8  mov     rbp, [rsp+58h+arg_8]
0x180009dad  mov     eax, ebx
0x180009daf  mov     rbx, [rsp+58h+arg_0]
0x180009db4  mov     rsi, [rsp+58h+arg_10]
0x180009db9  add     rsp, 50h
0x180009dbd  pop     rdi
0x180009dbe  retn
```
