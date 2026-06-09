# CDVRSink::MarkFileTemporary(int)

- ea: `0x1800043f0`
- end: `0x18000446c`
- name: `?MarkFileTemporary@CDVRSink@@UEAAJH@Z`
- size: `124`
- prototype: `__int64 __fastcall(CDVRSink *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800043f0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180004454`
- `KERNEL32!LeaveCriticalSection` at `0x180004454`
- `KERNEL32!EnterCriticalSection` at `0x18000440e`
- `KERNEL32!EnterCriticalSection` at `0x18000440e`

## pseudocode

```c
__int64 __fastcall CDVRSink::MarkFileTemporary(CDVRSink *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  unsigned int v5; // ebx
  int v6; // eax
  unsigned int v7; // ecx
  unsigned int v8; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 9224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 9224));
  if ( *((_DWORD *)this + 25) )
  {
    v5 = -2147418113;
  }
  else
  {
    v6 = *((_DWORD *)this - 2265);
    *((_DWORD *)this + 24) = a2;
    if ( a2 )
    {
      v7 = -2147475450;
      v8 = v6 | 7;
    }
    else
    {
      v7 = 0x80000000;
      v8 = v6 & 0xFFFFFFF8 | 3;
    }
    *((_DWORD *)this - 2265) = v8;
    *((_DWORD *)this - 2266) = v7;
    v5 = 0;
  }
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x1800043f0  mov     [rsp+arg_0], rbx
0x1800043f5  mov     [rsp+arg_8], rsi
0x1800043fa  push    rdi
0x1800043fb  sub     rsp, 20h
0x1800043ff  lea     rsi, [rcx-2408h]
0x180004406  mov     rbx, rcx
0x180004409  mov     rcx, rsi; lpCriticalSection
0x18000440c  mov     edi, edx
0x18000440e  call    cs:__imp_EnterCriticalSection
0x180004414  cmp     dword ptr [rbx+64h], 0
0x180004418  jz      short loc_180004421
0x18000441a  mov     ebx, 8000FFFFh
0x18000441f  jmp     short loc_180004451
0x180004421  mov     eax, [rbx-2364h]
0x180004427  mov     [rbx+60h], edi
0x18000442a  test    edi, edi
0x18000442c  jz      short loc_180004438
0x18000442e  mov     ecx, 80002006h
0x180004433  or      eax, 7
0x180004436  jmp     short loc_180004443
0x180004438  and     eax, 0FFFFFFFBh
0x18000443b  mov     ecx, 80000000h
0x180004440  or      eax, 3
0x180004443  mov     [rbx-2364h], eax
0x180004449  mov     [rbx-2368h], ecx
0x18000444f  xor     ebx, ebx
0x180004451  mov     rcx, rsi; lpCriticalSection
0x180004454  call    cs:__imp_LeaveCriticalSection
0x18000445a  mov     rsi, [rsp+28h+arg_8]
0x18000445f  mov     eax, ebx
0x180004461  mov     rbx, [rsp+28h+arg_0]
0x180004466  add     rsp, 20h
0x18000446a  pop     rdi
0x18000446b  retn
```
