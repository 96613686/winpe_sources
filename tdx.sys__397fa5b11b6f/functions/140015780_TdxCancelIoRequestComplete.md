# TdxCancelIoRequestComplete

- ea: `0x140015780`
- end: `0x1400157c4`
- name: `TdxCancelIoRequestComplete`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140015c20`

## callees

- `0x1400047d0`
- `0x1400054ec`
- `0x14000a908`
- `0x140015780`

## string_xrefs

- `0x140015792`: `TdxCancelIoRequestComplete`

## pseudocode

```c
void __fastcall TdxCancelIoRequestComplete(_DWORD *a1)
{
  int v1; // eax

  v1 = a1[1];
  if ( v1 == 2 )
  {
    DbgTdxDereferenceConnection((__int64)a1, (__int64)"TdxCancelIoRequestComplete", 516);
  }
  else if ( v1 == 1 )
  {
    DbgTdxDereferenceTransportAddress(a1, "minio\\netio\\session\\tdi\\request.c", 518);
  }
  else
  {
    TdxDereferenceControlChannel(a1);
  }
}

```

## disassembly

```asm
0x140015780  sub     rsp, 28h
0x140015784  mov     eax, [rcx+4]
0x140015787  cmp     eax, 2
0x14001578a  jnz     short loc_1400157A0
0x14001578c  mov     r8d, 204h
0x140015792  lea     rdx, aTdxcancelioreq; "TdxCancelIoRequestComplete"
0x140015799  call    DbgTdxDereferenceConnection
0x14001579e  jmp     short loc_1400157BE
0x1400157a0  cmp     eax, 1
0x1400157a3  jnz     short loc_1400157B9
0x1400157a5  mov     r8d, 206h
0x1400157ab  lea     rdx, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x1400157b2  call    DbgTdxDereferenceTransportAddress
0x1400157b7  jmp     short loc_1400157BE
0x1400157b9  call    TdxDereferenceControlChannel
0x1400157be  add     rsp, 28h
0x1400157c2  retn
```
