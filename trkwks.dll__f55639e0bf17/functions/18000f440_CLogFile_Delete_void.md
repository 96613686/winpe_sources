# CLogFile::Delete(void)

- ea: `0x18000f440`
- end: `0x18000f4b6`
- name: `?Delete@CLogFile@@QEAAXXZ`
- size: `118`
- prototype: `void __fastcall(const unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000756c`

## callees

- `0x1800015f0`
- `0x18000b3f0`
- `0x18000b4a0`
- `0x18000ebec`
- `0x18000f440`
- `0x180011000`

## pseudocode

```c
void __fastcall CLogFile::Delete(const unsigned __int16 **this)
{
  PRobustlyCreateableFile *v2; // rcx
  unsigned __int16 v3[264]; // [rsp+20h] [rbp-228h] BYREF

  CLogFile::CloseLog((CLogFile *)this);
  if ( (int)StringCchCopyW(v3, 0x105u, this[5]) >= 0
    && (int)StringCchCatW(v3, 0x105u, L"\\System Volume Information\\tracking.log") >= 0 )
  {
    PRobustlyCreateableFile::RobustlyDeleteFile(v2, v3);
  }
}

```

## disassembly

```asm
0x18000f440  push    rbx
0x18000f442  sub     rsp, 240h
0x18000f449  mov     rax, cs:__security_cookie
0x18000f450  xor     rax, rsp
0x18000f453  mov     [rsp+248h+var_18], rax
0x18000f45b  mov     rbx, rcx
0x18000f45e  call    ?CloseLog@CLogFile@@AEAAXXZ
0x18000f463  mov     r8, [rbx+28h]; unsigned __int16 *
0x18000f467  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x18000f46c  mov     ebx, 105h
0x18000f471  mov     edx, ebx; unsigned __int64
0x18000f473  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z
0x18000f478  test    eax, eax
0x18000f47a  js      short loc_18000F49D
0x18000f47c  lea     r8, ?s_tszLogFileName@@3QBGB
0x18000f483  mov     edx, ebx; unsigned __int64
0x18000f485  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x18000f48a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x18000f48f  test    eax, eax
0x18000f491  js      short loc_18000F49D
0x18000f493  lea     rdx, [rsp+248h+var_228]; unsigned __int16 *
0x18000f498  call    ?RobustlyDeleteFile@PRobustlyCreateableFile@@IEAAXPEBG@Z
0x18000f49d  mov     rcx, [rsp+248h+var_18]
0x18000f4a5  xor     rcx, rsp; StackCookie
0x18000f4a8  call    __security_check_cookie
0x18000f4ad  add     rsp, 240h
0x18000f4b4  pop     rbx
0x18000f4b5  retn
```
