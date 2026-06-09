# CBsString::_AllocateData(ulong,ushort * *,ulong *)

- ea: `0x1400103f0`
- end: `0x1400104a6`
- name: `?_AllocateData@CBsString@@CAJKPEAPEAGPEAK@Z`
- size: `182`
- prototype: `__int64 __fastcall(int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400100b4`

## callees

- `0x1400103f0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14001046c`
- `ole32!CoTaskMemAlloc` at `0x14001046c`

## pseudocode

```c
__int64 __fastcall CBsString::_AllocateData(int a1, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned __int16 *v8; // rax
  unsigned int v9; // ecx

  if ( a2
    && a3
    && ((v5 = a1 + 2, *a2 = 0, (unsigned int)(a1 + 2) > 0x100)
      ? (v5 > 0x400
       ? (v5 > 0x1000
        ? (v6 = (a1 + 4097) & 0xFFFFF000)
        : (v6 = (a1 + 1025) & 0xFFFFFC00))
       : (v6 = (a1 + 257) & 0xFFFFFF00))
      : (v6 = (a1 + 65) & 0xFFFFFFC0),
        v7 = v6 - 1,
        v6 - 1 <= 0xFFFFFFE) )
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v6);
    if ( v8 )
    {
      v9 = 0;
      *a2 = v8;
      *a3 = v7;
      *v8 = 0;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x1400103f0  mov     [rsp+arg_0], rbx
0x1400103f5  mov     [rsp+arg_8], rsi
0x1400103fa  push    rdi
0x1400103fb  sub     rsp, 20h
0x1400103ff  mov     rsi, r8
0x140010402  mov     rdi, rdx
0x140010405  test    rdx, rdx
0x140010408  jz      loc_14001048F
0x14001040e  test    r8, r8
0x140010411  jz      short loc_14001048F
0x140010413  lea     eax, [rcx+2]
0x140010416  mov     qword ptr [rdx], 0
0x14001041d  cmp     eax, 100h
0x140010422  ja      short loc_14001042C
0x140010424  add     eax, 3Fh ; '?'
0x140010427  and     eax, 0FFFFFFC0h
0x14001042a  jmp     short loc_14001045C
0x14001042c  cmp     eax, 400h
0x140010431  ja      short loc_14001043F
0x140010433  add     eax, 0FFh
0x140010438  and     eax, 0FFFFFF00h
0x14001043d  jmp     short loc_14001045C
0x14001043f  cmp     eax, 1000h
0x140010444  ja      short loc_140010452
0x140010446  add     eax, 3FFh
0x14001044b  and     eax, 0FFFFFC00h
0x140010450  jmp     short loc_14001045C
0x140010452  add     eax, 0FFFh
0x140010457  and     eax, 0FFFFF000h
0x14001045c  lea     ebx, [rax-1]
0x14001045f  cmp     ebx, 0FFFFFFEh
0x140010465  ja      short loc_14001048F
0x140010467  mov     ecx, eax
0x140010469  add     rcx, rcx; cb
0x14001046c  call    cs:__imp_CoTaskMemAlloc
0x140010472  mov     rdx, rax
0x140010475  test    rax, rax
0x140010478  jnz     short loc_140010481
0x14001047a  mov     ecx, 8007000Eh
0x14001047f  jmp     short loc_140010494
0x140010481  xor     ecx, ecx
0x140010483  mov     [rdi], rdx
0x140010486  xor     eax, eax
0x140010488  mov     [rsi], ebx
0x14001048a  mov     [rdx], ax
0x14001048d  jmp     short loc_140010494
0x14001048f  mov     ecx, 80070057h
0x140010494  mov     rbx, [rsp+28h+arg_0]
0x140010499  mov     eax, ecx
0x14001049b  mov     rsi, [rsp+28h+arg_8]
0x1400104a0  add     rsp, 20h
0x1400104a4  pop     rdi
0x1400104a5  retn
```
