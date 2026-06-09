# CBsString::_AllocateData(ulong,ushort * *,ulong *)

- ea: `0x18003548c`
- end: `0x180035501`
- name: `?_AllocateData@CBsString@@CAJKPEAPEAGPEAK@Z`
- size: `117`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034fe4`

## callees

- `0x18003548c`
- `0x1800355d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800354c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800354c7`

## pseudocode

```c
__int64 __fastcall CBsString::_AllocateData(__int64 a1, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // esi
  unsigned __int16 *v7; // rax
  unsigned int v8; // ecx

  if ( a2 && a3 && (*a2 = 0, v5 = CalculateRoundedUpBufferSize(), v6 = v5 - 1, v5 - 1 <= 0xFFFFFFE) )
  {
    v7 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v5);
    if ( v7 )
    {
      v8 = 0;
      *a2 = v7;
      *a3 = v6;
      *v7 = 0;
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
  return v8;
}

```

## disassembly

```asm
0x18003548c  mov     [rsp+arg_0], rbx
0x180035491  mov     [rsp+arg_8], rsi
0x180035496  push    rdi
0x180035497  sub     rsp, 20h
0x18003549b  mov     rdi, r8
0x18003549e  mov     rbx, rdx
0x1800354a1  test    rdx, rdx
0x1800354a4  jz      short loc_1800354EA
0x1800354a6  test    r8, r8
0x1800354a9  jz      short loc_1800354EA
0x1800354ab  mov     qword ptr [rdx], 0
0x1800354b2  call    _CalculateRoundedUpBufferSize
0x1800354b7  lea     esi, [rax-1]
0x1800354ba  cmp     esi, 0FFFFFFEh
0x1800354c0  ja      short loc_1800354EA
0x1800354c2  mov     ecx, eax
0x1800354c4  add     rcx, rcx; cb
0x1800354c7  call    cs:__imp_CoTaskMemAlloc
0x1800354cd  mov     rdx, rax
0x1800354d0  test    rax, rax
0x1800354d3  jnz     short loc_1800354DC
0x1800354d5  mov     ecx, 8007000Eh
0x1800354da  jmp     short loc_1800354EF
0x1800354dc  xor     ecx, ecx
0x1800354de  mov     [rbx], rdx
0x1800354e1  xor     eax, eax
0x1800354e3  mov     [rdi], esi
0x1800354e5  mov     [rdx], ax
0x1800354e8  jmp     short loc_1800354EF
0x1800354ea  mov     ecx, 80070057h
0x1800354ef  mov     rbx, [rsp+28h+arg_0]
0x1800354f4  mov     eax, ecx
0x1800354f6  mov     rsi, [rsp+28h+arg_8]
0x1800354fb  add     rsp, 20h
0x1800354ff  pop     rdi
0x180035500  retn
```
