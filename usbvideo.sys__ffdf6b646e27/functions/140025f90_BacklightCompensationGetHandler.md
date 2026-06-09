# BacklightCompensationGetHandler

- ea: `0x140025f90`
- end: `0x140026082`
- name: `BacklightCompensationGetHandler`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008640`
- `0x140008f80`
- `0x140025f90`

## pseudocode

```c
__int64 __fastcall BacklightCompensationGetHandler(IRP *a1, _DWORD *a2, int *a3)
{
  int v5; // eax
  __int64 v6; // rbx
  int NodeInfoAndValidate; // edx
  __int64 v8; // rcx
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  __int64 v12; // [rsp+50h] [rbp-20h] BYREF
  __int64 v13; // [rsp+58h] [rbp-18h] BYREF
  __int64 v14; // [rsp+60h] [rbp-10h] BYREF
  int v15; // [rsp+90h] [rbp+20h] BYREF
  int v16; // [rsp+98h] [rbp+28h] BYREF
  unsigned __int16 v17; // [rsp+A8h] [rbp+38h] BYREF

  LOBYTE(v16) = 0;
  v17 = 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  v5 = a2[5] & 0x10000000;
  LOBYTE(v15) = 0;
  v6 = v5 != 0 ? 8 : 0;
  NodeInfoAndValidate = GetNodeInfoAndValidate(a1, a2, a3, 1u, 5u, &v16, &v15, &v13, &v12, &v14);
  if ( NodeInfoAndValidate >= 0 )
  {
    LODWORD(Size) = 2;
    LOBYTE(v10) = v15;
    NodeInfoAndValidate = SubmitControlRequest(0xA1u, 0x81u, 0x100u, v16, v10, (unsigned __int8 *)&v17, Size, v13, v12);
    if ( NodeInfoAndValidate >= 0 )
    {
      v8 = v14;
      *(int *)((char *)a3 + v6 + 24) = v17;
      *(int *)((char *)a3 + v6 + 32) = *(_DWORD *)(v8 + 4);
      *(int *)((char *)a3 + v6 + 28) = *(_DWORD *)(v8 + 4);
    }
  }
  result = (unsigned int)NodeInfoAndValidate;
  a1->IoStatus.Status = NodeInfoAndValidate;
  return result;
}

```

## disassembly

```asm
0x140025f90  mov     r11, rsp
0x140025f93  mov     [r11+18h], rbx
0x140025f97  push    rbp
0x140025f98  push    rsi
0x140025f99  push    rdi
0x140025f9a  mov     rbp, rsp
0x140025f9d  sub     rsp, 70h
0x140025fa1  xor     eax, eax
0x140025fa3  mov     byte ptr [rbp+arg_8], 0
0x140025fa7  mov     [rbp+arg_18], ax
0x140025fab  mov     r9d, 1
0x140025fb1  mov     [rbp+var_10], rax
0x140025fb5  mov     rdi, r8
0x140025fb8  mov     [rbp+var_18], rax
0x140025fbc  mov     rsi, rcx
0x140025fbf  mov     [rbp+var_20], rax
0x140025fc3  mov     eax, [rdx+14h]
0x140025fc6  and     eax, 10000000h
0x140025fcb  mov     byte ptr [rbp+arg_0], 0
0x140025fcf  neg     eax
0x140025fd1  lea     rax, [rbp+var_10]
0x140025fd5  mov     [r11-40h], rax
0x140025fd9  sbb     rbx, rbx
0x140025fdc  lea     rax, [rbp+var_20]
0x140025fe0  and     ebx, 8
0x140025fe3  mov     [r11-48h], rax
0x140025fe7  lea     rax, [rbp+var_18]
0x140025feb  mov     [r11-50h], rax
0x140025fef  lea     rax, [rbp+arg_0]
0x140025ff3  mov     [r11-58h], rax
0x140025ff7  lea     rax, [rbp+arg_8]
0x140025ffb  mov     [r11-60h], rax
0x140025fff  mov     byte ptr [rsp+70h+var_50], 5
0x140026004  call    GetNodeInfoAndValidate
0x140026009  mov     edx, eax
0x14002600b  test    eax, eax
0x14002600d  js      short loc_14002606C
0x14002600f  mov     rax, [rbp+var_20]
0x140026013  mov     r8d, 100h; int
0x140026019  mov     r9b, byte ptr [rbp+arg_8]; int
0x14002601d  mov     dl, 81h; int
0x14002601f  mov     [rsp+70h+var_30], rax; __int64
0x140026024  mov     cl, 0A1h; int
0x140026026  mov     rax, [rbp+var_18]
0x14002602a  mov     [rsp+70h+var_38], rax; __int64
0x14002602f  lea     rax, [rbp+arg_18]
0x140026033  mov     dword ptr [rsp+70h+Size], 2; Size
0x14002603b  mov     [rsp+70h+var_48], rax; void *
0x140026040  mov     al, byte ptr [rbp+arg_0]
0x140026043  mov     byte ptr [rsp+70h+var_50], al; int
0x140026047  call    SubmitControlRequest
0x14002604c  mov     edx, eax
0x14002604e  test    eax, eax
0x140026050  js      short loc_14002606C
0x140026052  mov     rcx, [rbp+var_10]
0x140026056  movzx   eax, [rbp+arg_18]
0x14002605a  mov     [rbx+rdi+18h], eax
0x14002605e  mov     eax, [rcx+4]
0x140026061  mov     [rbx+rdi+20h], eax
0x140026065  mov     eax, [rcx+4]
0x140026068  mov     [rbx+rdi+1Ch], eax
0x14002606c  mov     rbx, [rsp+70h+arg_10]
0x140026074  mov     eax, edx
0x140026076  mov     [rsi+30h], edx
0x140026079  add     rsp, 70h
0x14002607d  pop     rdi
0x14002607e  pop     rsi
0x14002607f  pop     rbp
0x140026080  retn
```
