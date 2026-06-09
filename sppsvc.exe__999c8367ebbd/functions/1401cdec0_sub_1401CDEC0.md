# sub_1401CDEC0

- ea: `0x1401cdec0`
- end: `0x1401cdf12`
- name: `sub_1401CDEC0`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1401ce100`
- `0x1401ce150`

## callees

- `0x1401cdec0`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1401cdef9`
- `KERNEL32!SetThreadpoolTimer` at `0x1401cdef9`

## pseudocode

```c
void __fastcall sub_1401CDEC0(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_140446228 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x1401cdec0  sub     rsp, 28h
0x1401cdec4  test    rcx, rcx
0x1401cdec7  jz      short loc_1401CDF0C
0x1401cdec9  mov     eax, cs:dword_140446228
0x1401cdecf  test    eax, eax
0x1401cded1  jnz     short loc_1401CDF0C
0x1401cded3  mov     eax, edx
0x1401cded5  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1401cdedc  mov     rdx, rax
0x1401cdedf  shr     rdx, 20h
0x1401cdee3  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x1401cdee7  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1401cdeeb  mov     r9d, 1388h; msWindowLength
0x1401cdef1  xor     r8d, r8d; msPeriod
0x1401cdef4  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1401cdef9  call    cs:SetThreadpoolTimer
0x1401cdeff  jmp     short loc_1401CDF0C
0x1401cdf01  mov     eax, 1
0x1401cdf06  xchg    eax, cs:dword_140446228
0x1401cdf0c  add     rsp, 28h
0x1401cdf10  retn
0x14039112c  push    rbp
0x14039112e  sub     rsp, 20h
0x140391132  mov     rbp, rdx
0x140391135  mov     rax, [rcx]
0x140391138  xor     ecx, ecx
0x14039113a  cmp     dword ptr [rax], 0C000000Dh
0x140391140  setz    cl
0x140391143  mov     eax, ecx
0x140391145  add     rsp, 20h
0x140391149  pop     rbp
0x14039114a  retn
```
