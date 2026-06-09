# CWscAdmin::DoModalSecurityAction(HWND__ *,ulong)

- ea: `0x180003ad0`
- end: `0x180003b2d`
- name: `?DoModalSecurityAction@CWscAdmin@@UEAAJPEAUHWND__@@K@Z`
- size: `93`
- prototype: `__int64 __fastcall(CWscAdmin *__hidden this, HWND, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003ad0`
- `0x180003c78`
- `0x180003e38`
- `0x180006520`

## pseudocode

```c
__int64 __fastcall CWscAdmin::DoModalSecurityAction(CWscAdmin *this, HWND a2, int a3)
{
  unsigned int v6; // ebx

  CCriticalSection::Lock((CWscAdmin *)((char *)this + 32));
  v6 = 1;
  if ( !*((_DWORD *)this + 6) )
  {
    *((_DWORD *)this + 6) = 1;
    v6 = ExecuteSecurityActionHandler(a2, a3, 0, 1) == 0 ? 0x80004005 : 0;
  }
  CCriticalSection::Unlock((CWscAdmin *)((char *)this + 32));
  return v6;
}

```

## disassembly

```asm
0x180003ad0  push    rbx
0x180003ad2  push    rbp
0x180003ad3  push    rsi
0x180003ad4  push    rdi
0x180003ad5  push    r14
0x180003ad7  sub     rsp, 20h
0x180003adb  mov     rdi, rcx
0x180003ade  mov     ebp, r8d
0x180003ae1  add     rcx, 20h ; ' '; this
0x180003ae5  mov     r14, rdx
0x180003ae8  call    ?Lock@CCriticalSection@@QEAAXXZ; CCriticalSection::Lock(void)
0x180003aed  cmp     dword ptr [rdi+18h], 0
0x180003af1  mov     ebx, 1
0x180003af6  jnz     short loc_180003B17
0x180003af8  mov     r9b, bl
0x180003afb  mov     [rdi+18h], ebx
0x180003afe  xor     r8d, r8d
0x180003b01  mov     edx, ebp
0x180003b03  mov     rcx, r14
0x180003b06  call    ?ExecuteSecurityActionHandler@@YA_NPEAUHWND__@@W4SecurityAction@@PEAVSecurityLogicState@@_N@Z; ExecuteSecurityActionHandler(HWND__ *,SecurityAction,SecurityLogicState *,bool)
0x180003b0b  neg     al
0x180003b0d  sbb     ebx, ebx
0x180003b0f  not     ebx
0x180003b11  and     ebx, 80004005h
0x180003b17  lea     rcx, [rdi+20h]; this
0x180003b1b  call    ?Unlock@CCriticalSection@@QEAAXXZ; CCriticalSection::Unlock(void)
0x180003b20  mov     eax, ebx
0x180003b22  add     rsp, 20h
0x180003b26  pop     r14
0x180003b28  pop     rdi
0x180003b29  pop     rsi
0x180003b2a  pop     rbp
0x180003b2b  pop     rbx
0x180003b2c  retn
```
