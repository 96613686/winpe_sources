# TimecodeReaderGetHandler

- ea: `0x14002ed60`
- end: `0x14002eeb8`
- name: `TimecodeReaderGetHandler`
- size: `344`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140008640`
- `0x140008f80`
- `0x14002ed60`
- `0x140040e40`

## pseudocode

```c
__int64 __fastcall TimecodeReaderGetHandler(IRP *a1, _DWORD *a2, char *a3)
{
  int v4; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v7; // edx
  ULONG_PTR v10; // rbx
  int NodeInfoAndValidate; // edx
  int v12; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  __int64 v14; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+58h] [rbp-18h] BYREF
  __int64 v16; // [rsp+60h] [rbp-10h] BYREF
  int v17; // [rsp+A0h] [rbp+30h] BYREF
  int v18; // [rsp+A8h] [rbp+38h] BYREF
  int v19; // [rsp+B8h] [rbp+48h] BYREF

  v4 = a2[5] & 0x10000000;
  v19 = 0;
  LOBYTE(v18) = 0;
  LOBYTE(v17) = 0;
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v15 = 0;
  v14 = 0;
  v7 = v4 != 0 ? 56 : 48;
  if ( CurrentStackLocation->Parameters.Read.Length < v7 )
    return 3221225507LL;
  v10 = v7;
  memset(a3, 0, v7);
  a1->IoStatus.Information = v10;
  NodeInfoAndValidate = GetNodeInfoAndValidate(a1, a2, (int *)a3, 4u, 7u, &v18, &v17, &v15, &v14, &v16);
  if ( NodeInfoAndValidate >= 0 )
  {
    LODWORD(Size) = 4;
    LOBYTE(v12) = v17;
    NodeInfoAndValidate = SubmitControlRequest(0xA1u, 0x81u, 0x400u, v18, v12, (unsigned __int8 *)&v19, Size, v15, v14);
    if ( NodeInfoAndValidate >= 0 )
      *(_DWORD *)&a3[(v4 != 0 ? 8 : 0) + 36] = (v19 & 0x7F)
                                             + ((HIBYTE(v19) & 0x3F) << 24)
                                             + ((BYTE2(v19) & 0x7F) << 16)
                                             + ((BYTE1(v19) & 0x7F) << 8);
  }
  a1->IoStatus.Status = NodeInfoAndValidate;
  return (unsigned int)NodeInfoAndValidate;
}

```

## disassembly

```asm
0x14002ed60  mov     [rsp-28h+arg_10], rbx
0x14002ed65  push    rbp
0x14002ed66  push    rsi
0x14002ed67  push    rdi
0x14002ed68  push    r14
0x14002ed6a  push    r15
0x14002ed6c  mov     rbp, rsp
0x14002ed6f  sub     rsp, 70h
0x14002ed73  mov     edi, [rdx+14h]
0x14002ed76  mov     r14, rdx
0x14002ed79  and     edi, 10000000h
0x14002ed7f  mov     [rbp+arg_18], 0
0x14002ed86  mov     eax, edi
0x14002ed88  mov     byte ptr [rbp+arg_8], 0
0x14002ed8c  neg     eax
0x14002ed8e  mov     byte ptr [rbp+arg_0], 0
0x14002ed92  mov     rax, [rcx+0B8h]
0x14002ed99  mov     r15, r8
0x14002ed9c  sbb     edx, edx
0x14002ed9e  mov     [rbp+var_18], 0
0x14002eda6  and     edx, 8
0x14002eda9  mov     [rbp+var_20], 0
0x14002edb1  add     edx, 30h ; '0'
0x14002edb4  mov     rsi, rcx
0x14002edb7  cmp     [rax+8], edx
0x14002edba  jnb     short loc_14002EDC6
0x14002edbc  mov     eax, 0C0000023h
0x14002edc1  jmp     loc_14002EEA3
0x14002edc6  mov     ebx, edx
0x14002edc8  mov     rcx, r15; void *
0x14002edcb  mov     r8d, edx; Size
0x14002edce  xor     edx, edx; Val
0x14002edd0  call    memset
0x14002edd5  lea     rax, [rbp+var_10]
0x14002edd9  mov     [rsi+38h], rbx
0x14002eddd  mov     [rsp+70h+var_28], rax
0x14002ede2  mov     ebx, 4
0x14002ede7  lea     rax, [rbp+var_20]
0x14002edeb  mov     r9d, ebx
0x14002edee  mov     [rsp+70h+var_30], rax
0x14002edf3  mov     r8, r15
0x14002edf6  lea     rax, [rbp+var_18]
0x14002edfa  mov     rdx, r14
0x14002edfd  mov     [rsp+70h+var_38], rax
0x14002ee02  mov     rcx, rsi
0x14002ee05  lea     rax, [rbp+arg_0]
0x14002ee09  mov     [rsp+70h+Size], rax
0x14002ee0e  lea     rax, [rbp+arg_8]
0x14002ee12  mov     [rsp+70h+var_48], rax
0x14002ee17  mov     byte ptr [rsp+70h+var_50], 7
0x14002ee1c  call    GetNodeInfoAndValidate
0x14002ee21  mov     edx, eax
0x14002ee23  test    eax, eax
0x14002ee25  js      short loc_14002EE9E
0x14002ee27  mov     rax, [rbp+var_20]
0x14002ee2b  mov     r8d, 400h; int
0x14002ee31  mov     r9b, byte ptr [rbp+arg_8]; int
0x14002ee35  mov     dl, 81h; int
0x14002ee37  mov     [rsp+70h+var_30], rax; __int64
0x14002ee3c  mov     cl, 0A1h; int
0x14002ee3e  mov     rax, [rbp+var_18]
0x14002ee42  mov     [rsp+70h+var_38], rax; __int64
0x14002ee47  lea     rax, [rbp+arg_18]
0x14002ee4b  mov     dword ptr [rsp+70h+Size], ebx; Size
0x14002ee4f  mov     [rsp+70h+var_48], rax; void *
0x14002ee54  mov     al, byte ptr [rbp+arg_0]
0x14002ee57  mov     byte ptr [rsp+70h+var_50], al; int
0x14002ee5b  call    SubmitControlRequest
0x14002ee60  mov     edx, eax
0x14002ee62  test    eax, eax
0x14002ee64  js      short loc_14002EE9E
0x14002ee66  movzx   eax, byte ptr [rbp+arg_18+2]
0x14002ee6a  movzx   ecx, byte ptr [rbp+arg_18+1]
0x14002ee6e  and     eax, 7Fh
0x14002ee71  shl     eax, 10h
0x14002ee74  and     ecx, 7Fh
0x14002ee77  shl     ecx, 8
0x14002ee7a  add     ecx, eax
0x14002ee7c  movzx   eax, byte ptr [rbp+arg_18+3]
0x14002ee80  and     eax, 3Fh
0x14002ee83  shl     eax, 18h
0x14002ee86  add     ecx, eax
0x14002ee88  movzx   eax, byte ptr [rbp+arg_18]
0x14002ee8c  and     eax, 7Fh
0x14002ee8f  add     ecx, eax
0x14002ee91  neg     edi
0x14002ee93  sbb     rax, rax
0x14002ee96  and     eax, 8
0x14002ee99  mov     [rax+r15+24h], ecx
0x14002ee9e  mov     [rsi+30h], edx
0x14002eea1  mov     eax, edx
0x14002eea3  mov     rbx, [rsp+70h+arg_10]
0x14002eeab  add     rsp, 70h
0x14002eeaf  pop     r15
0x14002eeb1  pop     r14
0x14002eeb3  pop     rdi
0x14002eeb4  pop     rsi
0x14002eeb5  pop     rbp
0x14002eeb6  retn
```
