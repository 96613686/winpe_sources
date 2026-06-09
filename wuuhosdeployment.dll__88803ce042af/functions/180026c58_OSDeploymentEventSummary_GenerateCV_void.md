# OSDeploymentEventSummary::GenerateCV(void)

- ea: `0x180026c58`
- end: `0x180026dad`
- name: `?GenerateCV@OSDeploymentEventSummary@@QEAAXXZ`
- size: `341`
- prototype: `void __fastcall(OSDeploymentEventSummary *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180027430`

## callees

- `0x180005f64`
- `0x18000a6d0`
- `0x180026c58`
- `0x18002e0d0`
- `0x180042630`
- `0x1800492e0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180026c8f`
- `RPCRT4!UuidCreate` at `0x180026c8f`

## pseudocode

```c
void __fastcall OSDeploymentEventSummary::GenerateCV(OSDeploymentEventSummary *this)
{
  __int64 v2; // r9
  UUID *v3; // r10
  unsigned int v4; // r11d
  char Data1; // cl
  unsigned int v6; // edx
  unsigned __int64 Data1_low; // rax
  unsigned int v8; // r8d
  void *v9; // rcx
  char *v10; // rax
  UUID v11; // [rsp+20h] [rbp-69h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-59h] BYREF
  char v13[136]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v14; // [rsp+C8h] [rbp+3Fh]

  v13[130] = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  v13[129] = 17;
  v11 = Uuid;
  v14 = 0x1300000000LL;
  memset(v13, 0, 0x81u);
  v2 = 0;
  v3 = &v11;
  v4 = 0;
  do
  {
    Data1 = v3->Data1;
    v2 += 4;
    v6 = BYTE2(v3->Data1);
    Data1_low = LOBYTE(v3->Data1);
    v8 = BYTE1(v3->Data1);
    v3 = (UUID *)((char *)v3 + 3);
    ++v4;
    Uuid.Data4[v2 + 4] = `TLV::Base64Encode<129>'::`2'::s_lookupTable[Data1_low >> 2];
    Uuid.Data4[v2 + 5] = `TLV::Base64Encode<129>'::`2'::s_lookupTable[((unsigned __int64)v8 >> 4)
                                                                    | (unsigned __int8)(16 * (Data1 & 3))];
    Uuid.Data4[v2 + 6] = `TLV::Base64Encode<129>'::`2'::s_lookupTable[((unsigned __int64)v6 >> 6)
                                                                    | (unsigned __int8)(4 * (v8 & 0xF))];
    Uuid.Data4[v2 + 7] = `TLV::Base64Encode<129>'::`2'::s_lookupTable[v6 & 0x3F];
  }
  while ( v4 < 4 );
  v9 = (void *)*((_QWORD *)this + 1);
  v13[v2] = 0;
  strcpy(&v13[16], ".");
  if ( v9 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v9);
    *((_QWORD *)this + 1) = 0;
  }
  v10 = (char *)SafeSusAllocArray(0x81u, 1u);
  *((_QWORD *)this + 1) = v10;
  if ( v10 )
    TraceLoggingCorrelationVector::ToString((TraceLoggingCorrelationVector *)v13, v10);
}

```

## disassembly

```asm
0x180026c58  mov     [rsp-8+arg_8], rbx
0x180026c5d  mov     [rsp-8+arg_10], r15
0x180026c62  push    rbp
0x180026c63  lea     rbp, [rsp-57h]
0x180026c68  sub     rsp, 0E0h
0x180026c6f  mov     rax, cs:__security_cookie
0x180026c76  xor     rax, rsp
0x180026c79  mov     [rbp+57h+var_10], rax
0x180026c7d  mov     rbx, rcx
0x180026c80  mov     [rbp+57h+var_1E], 41h ; 'A'
0x180026c84  xorps   xmm0, xmm0
0x180026c87  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180026c8b  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180026c8f  call    cs:__imp_UuidCreate
0x180026c95  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x180026c99  lea     rcx, [rbp+57h+var_A0]; void *
0x180026c9d  mov     rax, 1300000000h
0x180026ca7  mov     [rbp+57h+var_1F], 11h
0x180026cab  xor     edx, edx; Val
0x180026cad  movdqa  [rbp+57h+var_C0], xmm0
0x180026cb2  mov     r8d, 81h; Size
0x180026cb8  mov     [rbp+57h+var_18], rax
0x180026cbc  call    memset
0x180026cc1  xor     r9d, r9d
0x180026cc4  lea     r10, [rbp+57h+var_C0]
0x180026cc8  xor     r11d, r11d
0x180026ccb  lea     r15, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBE_KAEAY0IB@D@Z@4QBDB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x180026cd2  movzx   ecx, byte ptr [r10]
0x180026cd6  lea     r9, [r9+4]
0x180026cda  movzx   edx, byte ptr [r10+2]
0x180026cdf  mov     eax, ecx
0x180026ce1  movzx   r8d, byte ptr [r10+1]
0x180026ce6  lea     r10, [r10+3]
0x180026cea  shr     rax, 2
0x180026cee  and     cl, 3
0x180026cf1  shl     cl, 4
0x180026cf4  inc     r11d
0x180026cf7  movzx   ecx, cl
0x180026cfa  mov     al, [rax+r15]
0x180026cfe  mov     [rbp+r9+57h+Uuid.Data4+4], al
0x180026d03  mov     eax, r8d
0x180026d06  shr     rax, 4
0x180026d0a  and     r8b, 0Fh
0x180026d0e  or      rcx, rax
0x180026d11  shl     r8b, 2
0x180026d15  mov     al, [rcx+r15]
0x180026d19  mov     [rbp+r9+57h+Uuid.Data4+5], al
0x180026d1e  mov     eax, edx
0x180026d20  shr     rax, 6
0x180026d24  and     edx, 3Fh
0x180026d27  movzx   ecx, r8b
0x180026d2b  or      rcx, rax
0x180026d2e  mov     al, [rcx+r15]
0x180026d32  mov     [rbp+r9+57h+Uuid.Data4+6], al
0x180026d37  mov     al, [rdx+r15]
0x180026d3b  mov     [rbp+r9+57h+Uuid.Data4+7], al
0x180026d40  cmp     r11d, 4
0x180026d44  jb      short loc_180026CD2
0x180026d46  mov     rcx, [rbx+8]; lpMem
0x180026d4a  mov     [rbp+r9+57h+var_A0], 0
0x180026d50  mov     word ptr [rbp+57h+var_90], 2Eh ; '.'
0x180026d56  test    rcx, rcx
0x180026d59  jz      short loc_180026D68
0x180026d5b  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180026d60  mov     qword ptr [rbx+8], 0
0x180026d68  mov     edx, 1; unsigned __int64
0x180026d6d  mov     ecx, 81h; unsigned __int64
0x180026d72  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180026d77  mov     [rbx+8], rax
0x180026d7b  test    rax, rax
0x180026d7e  jz      short loc_180026D8C
0x180026d80  mov     rdx, rax; char *
0x180026d83  lea     rcx, [rbp+57h+var_A0]; this
0x180026d87  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x180026d8c  mov     rcx, [rbp+57h+var_10]
0x180026d90  xor     rcx, rsp; StackCookie
0x180026d93  call    __security_check_cookie
0x180026d98  lea     r11, [rsp+0E0h+var_s0]
0x180026da0  mov     rbx, [r11+18h]
0x180026da4  mov     r15, [r11+20h]
0x180026da8  mov     rsp, r11
0x180026dab  pop     rbp
0x180026dac  retn
```
