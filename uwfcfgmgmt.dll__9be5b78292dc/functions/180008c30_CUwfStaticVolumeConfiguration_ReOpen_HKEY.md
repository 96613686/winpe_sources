# CUwfStaticVolumeConfiguration::ReOpen(HKEY__ *)

- ea: `0x180008c30`
- end: `0x180008cdb`
- name: `?ReOpen@CUwfStaticVolumeConfiguration@@QEAAJPEAUHKEY__@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(HKEY *this, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180008b3c`

## callees

- `0x1800054d0`
- `0x180008c30`
- `0x18000d5f0`
- `0x18000de30`
- `0x18000df60`
- `0x18001b020`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::ReOpen(HKEY *this, HKEY a2)
{
  __int64 result; // rax
  HKEY v5; // rax
  REGSAM v6; // r9d
  WCHAR SubKey[12]; // [rsp+30h] [rbp-28h] BYREF

  result = StringCchPrintfW(SubKey, 0xCu, L"%i", *((unsigned int *)this + 3));
  if ( (int)result >= 0 )
  {
    CUwfRegKey::Close(this + 2);
    v5 = this[3];
    v6 = *((_BYTE *)this + 9) != 0 ? 131097 : 131103;
    if ( *((_QWORD *)v5 + 1) == -1 )
      return CUwfRegKey::Open(this + 2, a2, SubKey, v6);
    else
      return CUwfRegKey::OpenTransacted(this + 2, a2, SubKey, v6, *((HANDLE *)v5 + 1));
  }
  return result;
}

```

## disassembly

```asm
0x180008c30  mov     [rsp+arg_10], rbx
0x180008c35  mov     [rsp+arg_18], rsi
0x180008c3a  push    rdi
0x180008c3b  sub     rsp, 50h
0x180008c3f  mov     rax, cs:__security_cookie
0x180008c46  xor     rax, rsp
0x180008c49  mov     [rsp+58h+var_10], rax
0x180008c4e  mov     r9d, [rcx+0Ch]
0x180008c52  lea     r8, aI; "%i"
0x180008c59  mov     rsi, rdx
0x180008c5c  mov     rbx, rcx
0x180008c5f  mov     edx, 0Ch; unsigned __int64
0x180008c64  lea     rcx, [rsp+58h+SubKey]; unsigned __int16 *
0x180008c69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008c6e  test    eax, eax
0x180008c70  js      short loc_180008CBE
0x180008c72  lea     rdi, [rbx+10h]
0x180008c76  mov     rcx, rdi; this
0x180008c79  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180008c7e  mov     al, [rbx+9]
0x180008c81  lea     r8, [rsp+58h+SubKey]; lpSubKey
0x180008c86  neg     al
0x180008c88  mov     rdx, rsi; hKey
0x180008c8b  mov     rax, [rbx+18h]
0x180008c8f  sbb     r9d, r9d
0x180008c92  and     r9d, 0FFFFFFFAh
0x180008c96  add     r9d, 2001Fh; samDesired
0x180008c9d  mov     rcx, [rax+8]
0x180008ca1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008ca5  jz      short loc_180008CB6
0x180008ca7  mov     [rsp+58h+var_38], rcx; HANDLE
0x180008cac  mov     rcx, rdi; phkResult
0x180008caf  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x180008cb4  jmp     short loc_180008CBE
0x180008cb6  mov     rcx, rdi; phkResult
0x180008cb9  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008cbe  mov     rcx, [rsp+58h+var_10]
0x180008cc3  xor     rcx, rsp; StackCookie
0x180008cc6  call    __security_check_cookie
0x180008ccb  mov     rbx, [rsp+58h+arg_10]
0x180008cd0  mov     rsi, [rsp+58h+arg_18]
0x180008cd5  add     rsp, 50h
0x180008cd9  pop     rdi
0x180008cda  retn
```
