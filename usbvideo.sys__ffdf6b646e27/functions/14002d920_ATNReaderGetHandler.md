# ATNReaderGetHandler

- ea: `0x14002d920`
- end: `0x14002da6e`
- name: `ATNReaderGetHandler`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140008640`
- `0x140008f80`
- `0x14002d920`
- `0x140040e40`

## pseudocode

```c
__int64 __fastcall ATNReaderGetHandler(IRP *a1, _DWORD *a2, char *a3)
{
  int v3; // edi
  int v5; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v9; // ecx
  ULONG_PTR v11; // rbx
  int NodeInfoAndValidate; // r9d
  int v13; // r8d
  int v14; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  __int64 v16; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+58h] [rbp-18h] BYREF
  __int64 v18; // [rsp+60h] [rbp-10h] BYREF
  int v19; // [rsp+A0h] [rbp+30h] BYREF
  int v20; // [rsp+A8h] [rbp+38h] BYREF
  _BYTE v21[5]; // [rsp+B8h] [rbp+48h] BYREF

  v3 = a2[5];
  memset(v21, 0, sizeof(v21));
  v5 = v3 & 0x10000000;
  v17 = 0;
  v16 = 0;
  LOBYTE(v20) = 0;
  LOBYTE(v19) = 0;
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v9 = v5 != 0 ? 56 : 48;
  if ( CurrentStackLocation->Parameters.Read.Length < v9 )
    return 3221225507LL;
  v11 = v9;
  memset(a3, 0, v9);
  a1->IoStatus.Information = v11;
  NodeInfoAndValidate = GetNodeInfoAndValidate(a1, a2, (int *)a3, 2u, 7u, &v20, &v19, &v17, &v16, &v18);
  if ( NodeInfoAndValidate >= 0 )
  {
    LODWORD(Size) = 5;
    LOBYTE(v14) = v19;
    NodeInfoAndValidate = SubmitControlRequest(0xA1u, 0x81u, 0x200u, v20, v14, v21, Size, v17, v16);
    if ( NodeInfoAndValidate >= 0 )
    {
      v13 = v21[1] & 1;
      *(_DWORD *)&a3[(v5 != 0 ? 8 : 0) + 36] = (*(_DWORD *)&v21[1] >> 1) & 0x7FFFFF;
      *(_DWORD *)&a3[(v5 != 0 ? 8 : 0) + 40] = v13;
    }
  }
  a1->IoStatus.Status = NodeInfoAndValidate;
  return (unsigned int)NodeInfoAndValidate;
}

```

## disassembly

```asm
0x14002d920  mov     [rsp-28h+arg_10], rbx
0x14002d925  push    rbp
0x14002d926  push    rsi
0x14002d927  push    rdi
0x14002d928  push    r14
0x14002d92a  push    r15
0x14002d92c  mov     rbp, rsp
0x14002d92f  sub     rsp, 70h
0x14002d933  mov     edi, [rdx+14h]
0x14002d936  xor     eax, eax
0x14002d938  mov     [rbp+arg_18], eax
0x14002d93b  mov     rsi, rcx
0x14002d93e  mov     [rbp+arg_1C], al
0x14002d941  and     edi, 10000000h
0x14002d947  mov     [rbp+var_18], rax
0x14002d94b  mov     r14, r8
0x14002d94e  mov     [rbp+var_20], rax
0x14002d952  mov     r15, rdx
0x14002d955  mov     eax, edi
0x14002d957  mov     byte ptr [rbp+arg_8], 0
0x14002d95b  neg     eax
0x14002d95d  mov     byte ptr [rbp+arg_0], 0
0x14002d961  mov     rax, [rsi+0B8h]
0x14002d968  sbb     ecx, ecx
0x14002d96a  and     ecx, 8
0x14002d96d  add     ecx, 30h ; '0'
0x14002d970  cmp     [rax+8], ecx
0x14002d973  jnb     short loc_14002D97F
0x14002d975  mov     eax, 0C0000023h
0x14002d97a  jmp     loc_14002DA59
0x14002d97f  mov     ebx, ecx
0x14002d981  xor     edx, edx; Val
0x14002d983  mov     r8d, ecx; Size
0x14002d986  mov     rcx, r14; void *
0x14002d989  call    memset
0x14002d98e  lea     rax, [rbp+var_10]
0x14002d992  mov     [rsi+38h], rbx
0x14002d996  mov     [rsp+70h+var_28], rax
0x14002d99b  mov     r9d, 2
0x14002d9a1  lea     rax, [rbp+var_20]
0x14002d9a5  mov     r8, r14
0x14002d9a8  mov     [rsp+70h+var_30], rax
0x14002d9ad  mov     rdx, r15
0x14002d9b0  lea     rax, [rbp+var_18]
0x14002d9b4  mov     rcx, rsi
0x14002d9b7  mov     [rsp+70h+var_38], rax
0x14002d9bc  lea     rax, [rbp+arg_0]
0x14002d9c0  mov     [rsp+70h+Size], rax
0x14002d9c5  lea     rax, [rbp+arg_8]
0x14002d9c9  mov     [rsp+70h+var_48], rax
0x14002d9ce  mov     byte ptr [rsp+70h+var_50], 7
0x14002d9d3  call    GetNodeInfoAndValidate
0x14002d9d8  mov     r9d, eax
0x14002d9db  test    eax, eax
0x14002d9dd  js      short loc_14002DA52
0x14002d9df  mov     rax, [rbp+var_20]
0x14002d9e3  mov     r8d, 200h; int
0x14002d9e9  mov     r9b, byte ptr [rbp+arg_8]; int
0x14002d9ed  mov     dl, 81h; int
0x14002d9ef  mov     [rsp+70h+var_30], rax; __int64
0x14002d9f4  mov     cl, 0A1h; int
0x14002d9f6  mov     rax, [rbp+var_18]
0x14002d9fa  mov     [rsp+70h+var_38], rax; __int64
0x14002d9ff  lea     rax, [rbp+arg_18]
0x14002da03  mov     dword ptr [rsp+70h+Size], 5; Size
0x14002da0b  mov     [rsp+70h+var_48], rax; void *
0x14002da10  mov     al, byte ptr [rbp+arg_0]
0x14002da13  mov     byte ptr [rsp+70h+var_50], al; int
0x14002da17  call    SubmitControlRequest
0x14002da1c  mov     r9d, eax
0x14002da1f  test    eax, eax
0x14002da21  js      short loc_14002DA52
0x14002da23  mov     r8d, [rbp+arg_18+1]
0x14002da27  mov     eax, edi
0x14002da29  mov     edx, r8d
0x14002da2c  shr     edx, 1
0x14002da2e  and     edx, 7FFFFFh
0x14002da34  neg     eax
0x14002da36  sbb     rcx, rcx
0x14002da39  and     r8d, 1
0x14002da3d  and     ecx, 8
0x14002da40  neg     edi
0x14002da42  sbb     rax, rax
0x14002da45  and     eax, 8
0x14002da48  mov     [rcx+r14+24h], edx
0x14002da4d  mov     [rax+r14+28h], r8d
0x14002da52  mov     [rsi+30h], r9d
0x14002da56  mov     eax, r9d
0x14002da59  mov     rbx, [rsp+70h+arg_10]
0x14002da61  add     rsp, 70h
0x14002da65  pop     r15
0x14002da67  pop     r14
0x14002da69  pop     rdi
0x14002da6a  pop     rsi
0x14002da6b  pop     rbp
0x14002da6c  retn
```
