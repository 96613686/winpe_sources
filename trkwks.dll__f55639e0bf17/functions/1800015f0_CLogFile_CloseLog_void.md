# CLogFile::CloseLog(void)

- ea: `0x1800015f0`
- end: `0x18000161d`
- name: `?CloseLog@CLogFile@@AEAAXXZ`
- size: `45`
- prototype: `void __fastcall(CLogFile *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000131c`
- `0x180001494`
- `0x180009720`
- `0x18000e7c0`
- `0x18000f440`

## callees

- `0x1800015f0`
- `0x180001624`

## pseudocode

```c
void __fastcall CLogFile::CloseLog(CLogFile *this)
{
  if ( *((_QWORD *)this + 2) )
  {
    *((_DWORD *)this + 20) &= ~1u;
    *((_QWORD *)this + 11) = 0;
    *((_DWORD *)this + 30) &= 0xFFFFFFFC;
    *((_QWORD *)this + 16) = 0;
    CSecureFile::CloseFile((CLogFile *)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x1800015f0  sub     rsp, 28h
0x1800015f4  xor     edx, edx
0x1800015f6  cmp     [rcx+10h], rdx
0x1800015fa  jz      short loc_180001618
0x1800015fc  and     dword ptr [rcx+50h], 0FFFFFFFEh
0x180001600  mov     [rcx+58h], rdx
0x180001604  and     dword ptr [rcx+78h], 0FFFFFFFCh
0x180001608  mov     [rcx+80h], rdx
0x18000160f  add     rcx, 10h; this
0x180001613  call    ?CloseFile@CSecureFile@@QEAAXXZ; CSecureFile::CloseFile(void)
0x180001618  add     rsp, 28h
0x18000161c  retn
```
