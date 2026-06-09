# PnpIrpQueryID(_DEVICE_OBJECT *,BUS_QUERY_ID_TYPE,ushort * *)

- ea: `0x1400092c8`
- end: `0x14000934c`
- name: `?PnpIrpQueryID@@YAJPEAU_DEVICE_OBJECT@@W4BUS_QUERY_ID_TYPE@@PEAPEAG@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, enum BUS_QUERY_ID_TYPE, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001e80`
- `0x140012010`

## callees

- `0x140009134`
- `0x1400092c8`
- `0x14000ab00`

## pseudocode

```c
__int64 __fastcall PnpIrpQueryID(struct _DEVICE_OBJECT *a1, ULONG a2, unsigned __int16 **a3)
{
  __int64 v6; // r9
  __int64 result; // rax
  unsigned __int64 v8; // [rsp+28h] [rbp-70h]
  struct _IO_STACK_LOCATION v9; // [rsp+40h] [rbp-58h] BYREF

  *a3 = 0;
  memset(&v9, 0, sizeof(v9));
  *(_WORD *)&v9.MajorFunction = 4891;
  v9.Parameters.Read.Length = a2;
  result = IopSynchronousCall(a1, &v9, 0, v6, 1, v8, (unsigned __int64 *)a3);
  if ( (int)result < 0 )
  {
    *a3 = 0;
  }
  else if ( !*a3 )
  {
    return 3221225659LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400092c8  mov     [rsp+arg_0], rbx
0x1400092cd  mov     [rsp+arg_8], rsi
0x1400092d2  push    rdi
0x1400092d3  sub     rsp, 90h
0x1400092da  mov     ebx, edx
0x1400092dc  mov     qword ptr [r8], 0
0x1400092e3  xor     edx, edx; Val
0x1400092e5  mov     rsi, r8
0x1400092e8  mov     rdi, rcx
0x1400092eb  lea     rcx, [rsp+98h+var_58]; void *
0x1400092f0  lea     r8d, [rdx+48h]; Size
0x1400092f4  call    memset
0x1400092f9  xor     r8d, r8d; void *
0x1400092fc  mov     [rsp+98h+var_68], rsi; unsigned __int64 *
0x140009301  lea     rdx, [rsp+98h+var_58]; struct _IO_STACK_LOCATION *
0x140009306  mov     word ptr [rsp+98h+var_58.MajorFunction], 131Bh
0x14000930d  mov     rcx, rdi; struct _DEVICE_OBJECT *
0x140009310  mov     dword ptr [rsp+98h+var_58.Parameters], ebx
0x140009314  mov     [rsp+98h+var_78], 1; char
0x140009319  call    ?IopSynchronousCall@@YAJPEAU_DEVICE_OBJECT@@PEAU_IO_STACK_LOCATION@@PEAXJE_KPEA_K@Z; IopSynchronousCall(_DEVICE_OBJECT *,_IO_STACK_LOCATION *,void *,long,uchar,unsigned __int64,unsigned __int64 *)
0x14000931e  test    eax, eax
0x140009320  js      short loc_14000932F
0x140009322  cmp     qword ptr [rsi], 0
0x140009326  jnz     short loc_140009336
0x140009328  mov     eax, 0C00000BBh
0x14000932d  jmp     short loc_140009336
0x14000932f  mov     qword ptr [rsi], 0
0x140009336  lea     r11, [rsp+98h+var_8]
0x14000933e  mov     rbx, [r11+10h]
0x140009342  mov     rsi, [r11+18h]
0x140009346  mov     rsp, r11
0x140009349  pop     rdi
0x14000934a  retn
```
