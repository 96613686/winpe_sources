# BacklightCompensationSetHandler

- ea: `0x140026090`
- end: `0x140026163`
- name: `BacklightCompensationSetHandler`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008640`
- `0x140008f80`
- `0x140026090`

## pseudocode

```c
__int64 __fastcall BacklightCompensationSetHandler(IRP *a1, _DWORD *a2, int *a3)
{
  int v5; // eax
  __int64 v6; // rbx
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-40h]
  size_t Size; // [rsp+30h] [rbp-30h]
  __int64 v10; // [rsp+50h] [rbp-10h] BYREF
  __int64 v11; // [rsp+58h] [rbp-8h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF
  int v13; // [rsp+88h] [rbp+28h] BYREF
  __int16 v14; // [rsp+98h] [rbp+38h] BYREF

  v14 = 0;
  v11 = 0;
  v10 = 0;
  v5 = a2[5] & 0x10000000;
  LOBYTE(v13) = 0;
  LOBYTE(v12) = 0;
  v6 = v5 != 0 ? 8 : 0;
  result = GetNodeInfoAndValidate(a1, a2, a3, 1u, 5u, &v13, &v12, &v11, &v10, 0);
  if ( (int)result >= 0 )
  {
    v14 = *(_WORD *)((char *)a3 + v6 + 24);
    LODWORD(Size) = 2;
    LOBYTE(v8) = v12;
    result = SubmitControlRequest(0x21u, 1u, 0x100u, v13, v8, (unsigned __int8 *)&v14, Size, v11, v10);
  }
  a1->IoStatus.Status = result;
  return result;
}

```

## disassembly

```asm
0x140026090  mov     r11, rsp
0x140026093  mov     [r11+18h], rbx
0x140026097  push    rbp
0x140026098  push    rsi
0x140026099  push    rdi
0x14002609a  mov     rbp, rsp
0x14002609d  sub     rsp, 60h
0x1400260a1  xor     eax, eax
0x1400260a3  mov     qword ptr [r11-30h], 0
0x1400260ab  mov     [rbp+arg_18], ax
0x1400260af  mov     r9d, 1
0x1400260b5  mov     [rbp+var_8], rax
0x1400260b9  mov     rsi, r8
0x1400260bc  mov     [rbp+var_10], rax
0x1400260c0  mov     rdi, rcx
0x1400260c3  mov     eax, [rdx+14h]
0x1400260c6  and     eax, 10000000h
0x1400260cb  mov     byte ptr [rbp+arg_8], 0
0x1400260cf  neg     eax
0x1400260d1  mov     byte ptr [rbp+arg_0], 0
0x1400260d5  lea     rax, [rbp+var_10]
0x1400260d9  mov     [r11-38h], rax
0x1400260dd  sbb     rbx, rbx
0x1400260e0  lea     rax, [rbp+var_8]
0x1400260e4  and     ebx, 8
0x1400260e7  mov     [r11-40h], rax
0x1400260eb  lea     rax, [rbp+arg_0]
0x1400260ef  mov     [r11-48h], rax
0x1400260f3  lea     rax, [rbp+arg_8]
0x1400260f7  mov     [r11-50h], rax
0x1400260fb  mov     byte ptr [rsp+60h+var_40], 5
0x140026100  call    GetNodeInfoAndValidate
0x140026105  test    eax, eax
0x140026107  js      short loc_14002614F
0x140026109  movzx   eax, word ptr [rbx+rsi+18h]
0x14002610e  mov     r8d, 100h; int
0x140026114  mov     r9b, byte ptr [rbp+arg_8]; int
0x140026118  mov     dl, 1; int
0x14002611a  mov     [rbp+arg_18], ax
0x14002611e  mov     cl, 21h ; '!'; int
0x140026120  mov     rax, [rbp+var_10]
0x140026124  mov     [rsp+60h+var_20], rax; __int64
0x140026129  mov     rax, [rbp+var_8]
0x14002612d  mov     [rsp+60h+var_28], rax; __int64
0x140026132  lea     rax, [rbp+arg_18]
0x140026136  mov     dword ptr [rsp+60h+Size], 2; Size
0x14002613e  mov     [rsp+60h+var_38], rax; void *
0x140026143  mov     al, byte ptr [rbp+arg_0]
0x140026146  mov     byte ptr [rsp+60h+var_40], al; int
0x14002614a  call    SubmitControlRequest
0x14002614f  mov     rbx, [rsp+60h+arg_10]
0x140026157  mov     [rdi+30h], eax
0x14002615a  add     rsp, 60h
0x14002615e  pop     rdi
0x14002615f  pop     rsi
0x140026160  pop     rbp
0x140026161  retn
```
