# CBsString::_AllocateData(ulong,ushort * *,ulong *)

- ea: `0x18001fe30`
- end: `0x18001fee6`
- name: `?_AllocateData@CBsString@@CAJKPEAPEAGPEAK@Z`
- size: `182`
- prototype: `__int64 __fastcall(int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f7f8`

## callees

- `0x18001fe30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001feac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001feac`

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
0x18001fe30  mov     [rsp+arg_0], rbx
0x18001fe35  mov     [rsp+arg_8], rsi
0x18001fe3a  push    rdi
0x18001fe3b  sub     rsp, 20h
0x18001fe3f  mov     rsi, r8
0x18001fe42  mov     rdi, rdx
0x18001fe45  test    rdx, rdx
0x18001fe48  jz      loc_18001FECF
0x18001fe4e  test    r8, r8
0x18001fe51  jz      short loc_18001FECF
0x18001fe53  lea     eax, [rcx+2]
0x18001fe56  mov     qword ptr [rdx], 0
0x18001fe5d  cmp     eax, 100h
0x18001fe62  ja      short loc_18001FE6C
0x18001fe64  add     eax, 3Fh ; '?'
0x18001fe67  and     eax, 0FFFFFFC0h
0x18001fe6a  jmp     short loc_18001FE9C
0x18001fe6c  cmp     eax, 400h
0x18001fe71  ja      short loc_18001FE7F
0x18001fe73  add     eax, 0FFh
0x18001fe78  and     eax, 0FFFFFF00h
0x18001fe7d  jmp     short loc_18001FE9C
0x18001fe7f  cmp     eax, 1000h
0x18001fe84  ja      short loc_18001FE92
0x18001fe86  add     eax, 3FFh
0x18001fe8b  and     eax, 0FFFFFC00h
0x18001fe90  jmp     short loc_18001FE9C
0x18001fe92  add     eax, 0FFFh
0x18001fe97  and     eax, 0FFFFF000h
0x18001fe9c  lea     ebx, [rax-1]
0x18001fe9f  cmp     ebx, 0FFFFFFEh
0x18001fea5  ja      short loc_18001FECF
0x18001fea7  mov     ecx, eax
0x18001fea9  add     rcx, rcx; cb
0x18001feac  call    cs:__imp_CoTaskMemAlloc
0x18001feb2  mov     rdx, rax
0x18001feb5  test    rax, rax
0x18001feb8  jnz     short loc_18001FEC1
0x18001feba  mov     ecx, 8007000Eh
0x18001febf  jmp     short loc_18001FED4
0x18001fec1  xor     ecx, ecx
0x18001fec3  mov     [rdi], rdx
0x18001fec6  xor     eax, eax
0x18001fec8  mov     [rsi], ebx
0x18001feca  mov     [rdx], ax
0x18001fecd  jmp     short loc_18001FED4
0x18001fecf  mov     ecx, 80070057h
0x18001fed4  mov     rbx, [rsp+28h+arg_0]
0x18001fed9  mov     eax, ecx
0x18001fedb  mov     rsi, [rsp+28h+arg_8]
0x18001fee0  add     rsp, 20h
0x18001fee4  pop     rdi
0x18001fee5  retn
```
