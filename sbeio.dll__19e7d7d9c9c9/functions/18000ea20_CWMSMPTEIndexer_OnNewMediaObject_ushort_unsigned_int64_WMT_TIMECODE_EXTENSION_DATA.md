# CWMSMPTEIndexer::OnNewMediaObject(ushort,unsigned __int64,_WMT_TIMECODE_EXTENSION_DATA &)

- ea: `0x18000ea20`
- end: `0x18000eb3a`
- name: `?OnNewMediaObject@CWMSMPTEIndexer@@UEAAJG_KAEAU_WMT_TIMECODE_EXTENSION_DATA@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(CWMSMPTEIndexer *__hidden this, unsigned __int16, unsigned __int64, struct _WMT_TIMECODE_EXTENSION_DATA *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180007e38`
- `0x18000ea20`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CWMSMPTEIndexer::OnNewMediaObject(
        CWMSMPTEIndexer *this,
        unsigned __int16 a2,
        __int64 a3,
        struct _WMT_TIMECODE_EXTENSION_DATA *a4)
{
  __int64 v4; // rbx
  WORD wRange; // r12
  __int64 v10; // rbp
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned int v14; // esi
  __int64 v15; // rax

  v4 = a2;
  if ( a2 >= 0x3Fu )
    return 2147942487LL;
  wRange = a4->wRange;
  v10 = (*(__int64 (__fastcall **)(CWMSMPTEIndexer *, _QWORD))(*(_QWORD *)this + 64LL))(this, a4->wRange);
  if ( v10 )
  {
    _mm_lfence();
    v12 = *((unsigned int *)this + v4 + 60);
    if ( (_DWORD)v12 == -1 )
    {
      return (unsigned int)-1072889805;
    }
    else
    {
      v13 = CTPtrArray<unsigned char,20>::operator[]((char *)this + 16, v12);
      if ( v13 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v13 + 16LL))(v13, a3, wRange);
        if ( v11 >= 0 )
        {
          v11 = (*(__int64 (__fastcall **)(char *, struct _WMT_TIMECODE_EXTENSION_DATA *))(*((_QWORD *)this + 91) + 32LL))(
                  (char *)this + 728,
                  a4);
          if ( v11 >= 0 )
          {
            ++*((_QWORD *)this + 62);
            v14 = 0;
            if ( *((_DWORD *)this + 58) )
            {
              while ( 1 )
              {
                v15 = CTPtrArray<unsigned char,20>::operator[]((char *)this + 16, v14);
                if ( v15 )
                {
                  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, wRange);
                  if ( v11 < 0 )
                    break;
                }
                if ( ++v14 >= *((_DWORD *)this + 58) )
                  goto LABEL_15;
              }
            }
            else
            {
LABEL_15:
              ++*(_DWORD *)(v10 + 16);
            }
          }
        }
      }
      else
      {
        return (unsigned int)-2147418113;
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000ea20  push    rbx
0x18000ea22  push    rbp
0x18000ea23  push    rsi
0x18000ea24  push    rdi
0x18000ea25  push    r12
0x18000ea27  push    r14
0x18000ea29  push    r15
0x18000ea2b  sub     rsp, 20h
0x18000ea2f  movzx   ebx, dx
0x18000ea32  mov     r14, r9
0x18000ea35  mov     rsi, r8
0x18000ea38  mov     rdi, rcx
0x18000ea3b  cmp     ebx, 3Fh ; '?'
0x18000ea3e  jb      short loc_18000EA4A
0x18000ea40  mov     eax, 80070057h
0x18000ea45  jmp     loc_18000EB2B
0x18000ea4a  mov     rax, [rcx]
0x18000ea4d  movzx   r12d, word ptr [r9]
0x18000ea51  movzx   edx, r12w
0x18000ea55  mov     rax, [rax+40h]
0x18000ea59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea5e  mov     rbp, rax
0x18000ea61  test    rax, rax
0x18000ea64  jnz     short loc_18000EA70
0x18000ea66  mov     ebx, 80004005h
0x18000ea6b  jmp     loc_18000EB29
0x18000ea70  lfence
0x18000ea73  mov     edx, [rdi+rbx*4+0F0h]
0x18000ea7a  cmp     edx, 0FFFFFFFFh
0x18000ea7d  jnz     short loc_18000EA89
0x18000ea7f  mov     ebx, 0C00D0033h
0x18000ea84  jmp     loc_18000EB29
0x18000ea89  lea     rcx, [rdi+10h]
0x18000ea8d  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000ea92  mov     rcx, rax
0x18000ea95  test    rax, rax
0x18000ea98  jnz     short loc_18000EAA4
0x18000ea9a  mov     ebx, 8000FFFFh
0x18000ea9f  jmp     loc_18000EB29
0x18000eaa4  mov     rax, [rax]
0x18000eaa7  movzx   r8d, r12w
0x18000eaab  mov     rdx, rsi
0x18000eaae  mov     rax, [rax+10h]
0x18000eab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eab7  mov     ebx, eax
0x18000eab9  test    eax, eax
0x18000eabb  js      short loc_18000EB29
0x18000eabd  lea     rcx, [rdi+2D8h]
0x18000eac4  mov     rdx, r14
0x18000eac7  mov     rax, [rcx]
0x18000eaca  mov     rax, [rax+20h]
0x18000eace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ead3  mov     ebx, eax
0x18000ead5  test    eax, eax
0x18000ead7  js      short loc_18000EB29
0x18000ead9  inc     qword ptr [rdi+1F0h]
0x18000eae0  xor     esi, esi
0x18000eae2  cmp     [rdi+0E8h], esi
0x18000eae8  jbe     short loc_18000EB26
0x18000eaea  mov     edx, esi
0x18000eaec  lea     rcx, [rdi+10h]
0x18000eaf0  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000eaf5  mov     r8, rax
0x18000eaf8  test    rax, rax
0x18000eafb  jz      short loc_18000EB16
0x18000eafd  mov     rcx, [rax]
0x18000eb00  movzx   edx, r12w
0x18000eb04  mov     rax, [rcx+18h]
0x18000eb08  mov     rcx, r8
0x18000eb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb10  mov     ebx, eax
0x18000eb12  test    eax, eax
0x18000eb14  js      short loc_18000EB29
0x18000eb16  inc     esi
0x18000eb18  mov     eax, ebx
0x18000eb1a  cmp     esi, [rdi+0E8h]
0x18000eb20  jb      short loc_18000EAEA
0x18000eb22  test    eax, eax
0x18000eb24  js      short loc_18000EB29
0x18000eb26  inc     dword ptr [rbp+10h]
0x18000eb29  mov     eax, ebx
0x18000eb2b  add     rsp, 20h
0x18000eb2f  pop     r15
0x18000eb31  pop     r14
0x18000eb33  pop     r12
0x18000eb35  pop     rdi
0x18000eb36  pop     rsi
0x18000eb37  pop     rbp
0x18000eb38  pop     rbx
0x18000eb39  retn
```
