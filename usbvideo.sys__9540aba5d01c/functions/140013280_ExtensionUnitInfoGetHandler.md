# ExtensionUnitInfoGetHandler

- ea: `0x140013280`
- end: `0x140013345`
- name: `ExtensionUnitInfoGetHandler`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140008f80`
- `0x140013280`
- `0x140040b40`

## pseudocode

```c
__int64 __fastcall ExtensionUnitInfoGetHandler(IRP *a1, __int64 a2, int *a3)
{
  unsigned __int16 v3; // r9
  int NodeInfoAndValidate; // edi
  unsigned __int8 *v7; // r8
  unsigned int Length; // edx
  ULONG_PTR v9; // rax
  ULONG_PTR v10; // rbx
  __int64 result; // rax
  __int64 v12; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v13[4]; // [rsp+58h] [rbp-20h] BYREF
  char v14; // [rsp+80h] [rbp+8h] BYREF
  char v15; // [rsp+88h] [rbp+10h] BYREF
  __int64 v16; // [rsp+98h] [rbp+20h] BYREF

  v3 = *(_WORD *)(a2 + 16);
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v12 = 0;
  NodeInfoAndValidate = GetNodeInfoAndValidate(a1, (_DWORD *)a2, a3, v3, 9u, &v15, &v14, &v16, &v12, v13);
  if ( NodeInfoAndValidate >= 0 )
  {
    v7 = *(unsigned __int8 **)(v16 + 32);
    Length = a1->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
    v9 = (unsigned int)*v7 - 4;
    if ( Length )
    {
      if ( Length >= (unsigned int)v9 )
      {
        v10 = (unsigned int)v9;
        memmove(a3, v7 + 4, (unsigned int)v9);
        a1->IoStatus.Information = v10;
      }
      else
      {
        NodeInfoAndValidate = -1073741789;
      }
    }
    else
    {
      a1->IoStatus.Information = v9;
      NodeInfoAndValidate = -2147483643;
    }
  }
  result = (unsigned int)NodeInfoAndValidate;
  a1->IoStatus.Status = NodeInfoAndValidate;
  return result;
}

```

## disassembly

```asm
0x140013280  mov     r11, rsp
0x140013283  mov     [r11+18h], rbx
0x140013287  push    rbp
0x140013288  push    rsi
0x140013289  push    rdi
0x14001328a  sub     rsp, 60h
0x14001328e  movzx   r9d, word ptr [rdx+10h]
0x140013293  lea     rax, [r11-20h]
0x140013297  mov     [r11-30h], rax
0x14001329b  xor     ebx, ebx
0x14001329d  lea     rax, [r11-28h]
0x1400132a1  mov     [r11+10h], bl
0x1400132a5  mov     [r11-38h], rax
0x1400132a9  mov     rbp, r8
0x1400132ac  lea     rax, [r11+20h]
0x1400132b0  mov     [r11+8], bl
0x1400132b4  mov     [r11-40h], rax
0x1400132b8  mov     rsi, rcx
0x1400132bb  lea     rax, [r11+8]
0x1400132bf  mov     [r11+20h], rbx
0x1400132c3  mov     [r11-48h], rax
0x1400132c7  lea     rax, [r11+10h]
0x1400132cb  mov     [r11-50h], rax
0x1400132cf  mov     [rsp+78h+var_58], 9
0x1400132d4  mov     [r11-28h], rbx
0x1400132d8  call    GetNodeInfoAndValidate
0x1400132dd  mov     edi, eax
0x1400132df  test    eax, eax
0x1400132e1  js      short loc_14001332F
0x1400132e3  mov     rcx, [rsp+78h+arg_18]
0x1400132eb  mov     r8, [rcx+20h]
0x1400132ef  mov     rcx, [rsi+0B8h]
0x1400132f6  movzx   eax, byte ptr [r8]
0x1400132fa  mov     edx, [rcx+8]
0x1400132fd  add     eax, 0FFFFFFFCh
0x140013300  test    edx, edx
0x140013302  jnz     short loc_14001330F
0x140013304  mov     [rsi+38h], rax
0x140013308  mov     edi, 80000005h
0x14001330d  jmp     short loc_14001332F
0x14001330f  cmp     edx, eax
0x140013311  jnb     short loc_14001331A
0x140013313  mov     edi, 0C0000023h
0x140013318  jmp     short loc_14001332F
0x14001331a  lea     rdx, [r8+4]; Src
0x14001331e  mov     ebx, eax
0x140013320  mov     r8d, eax; Size
0x140013323  mov     rcx, rbp; void *
0x140013326  call    memmove
0x14001332b  mov     [rsi+38h], rbx
0x14001332f  mov     rbx, [rsp+78h+arg_10]
0x140013337  mov     eax, edi
0x140013339  mov     [rsi+30h], edi
0x14001333c  add     rsp, 60h
0x140013340  pop     rdi
0x140013341  pop     rsi
0x140013342  pop     rbp
0x140013343  retn
```
