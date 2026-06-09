# WriterTemplateTable::WriteTemplate(WriteBuffer &,BinXmlTemplate const &)

- ea: `0x180035a00`
- end: `0x180035bc5`
- name: `?WriteTemplate@WriterTemplateTable@@UEAAXAEAVWriteBuffer@@AEBVBinXmlTemplate@@@Z`
- size: `453`
- prototype: `void(WriterTemplateTable *__hidden this, struct WriteBuffer *, const struct BinXmlTemplate *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180003780`
- `0x180013650`
- `0x180019fac`
- `0x180023548`
- `0x180023ac8`
- `0x180024a50`
- `0x180030454`
- `0x18003057c`
- `0x180033d28`
- `0x180035a00`
- `0x180038fa4`

## pseudocode

```c
void __fastcall WriterTemplateTable::WriteTemplate(
        WriterTemplateTable *this,
        struct WriteBuffer *a2,
        const struct BinXmlTemplate *a3)
{
  char v6; // al
  __int64 v7; // rdx
  __int64 v8; // rsi
  unsigned int v9; // r10d
  const char *v10; // r8
  unsigned int v11; // r10d
  __int64 v12; // rcx
  unsigned int *v13; // r14
  unsigned int v14; // edx
  bool v15; // r8
  unsigned int v16; // [rsp+20h] [rbp-50h] BYREF
  int v17; // [rsp+24h] [rbp-4Ch] BYREF
  __int64 v18; // [rsp+28h] [rbp-48h] BYREF
  int v19; // [rsp+30h] [rbp-40h]
  int v20; // [rsp+34h] [rbp-3Ch]
  __int128 pExceptionObject; // [rsp+38h] [rbp-38h] BYREF
  __int128 v22; // [rsp+48h] [rbp-28h]
  __int128 v23; // [rsp+58h] [rbp-18h]

  v6 = utl::_HashBytes((const struct BinXmlTemplate *)((char *)a3 + 16), (const void *)0x10, (unsigned __int64)a3);
  v7 = *((_QWORD *)this + 18);
  v8 = v6 & 0x1F;
  v9 = *(_DWORD *)(*((_QWORD *)this + 1) + 4 * v8);
  v16 = v9;
  v10 = (const char *)(unsigned int)(*(_DWORD *)(v7 + 32) - *(_DWORD *)(v7 + 24));
  if ( v9 >= (int)v10 - 4 || LoopExists(v9, *(const unsigned __int8 **)(v7 + 24), (unsigned int)v10) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b0a585e5e25b3fab73f596ff3bcfdc94_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xDu, v10, 35);
    throw (EvtException *)&pExceptionObject;
  }
  while ( v11 )
  {
    v12 = *((_QWORD *)this + 18);
    v19 = 0;
    v13 = (unsigned int *)(*(_QWORD *)(v12 + 24) + v11);
    v18 = *(_QWORD *)(v12 + 24);
    v14 = (_DWORD)v13 - *(_DWORD *)(v12 + 24) + 4;
    v20 = *(_DWORD *)(v12 + 32) - *(_DWORD *)(v12 + 24);
    UserBuffer::Advance((UserBuffer *)&v18, v14);
    pExceptionObject = 0;
    v22 = 0;
    v23 = 0;
    BinXmlTemplate::Deserialize((BinXmlTemplate *)&pExceptionObject, (struct UserBuffer *)&v18);
    if ( v22 == *((_OWORD *)a3 + 1) )
    {
      WriteBuffer::Write(a2, &v16, 4u);
      return;
    }
    v11 = *v13;
    v16 = *v13;
  }
  v17 = *((_DWORD *)a2 + 4) + 4;
  WriteBuffer::Write(a2, &v17, 4u);
  WriteBuffer::Write(a2, (const void *)(*((_QWORD *)this + 1) + 4 * v8), 4u);
  *(_DWORD *)(*((_QWORD *)this + 1) + 4 * v8) = v17;
  BinXmlTemplate::Serialize(a3, a2, v15);
}

```

## disassembly

```asm
0x180035a00  push    rbp
0x180035a02  push    rbx
0x180035a03  push    rsi
0x180035a04  push    rdi
0x180035a05  push    r13
0x180035a07  push    r14
0x180035a09  push    r15
0x180035a0b  mov     rbp, rsp
0x180035a0e  sub     rsp, 70h
0x180035a12  mov     rax, cs:__security_cookie
0x180035a19  xor     rax, rsp
0x180035a1c  mov     [rbp+var_8], rax
0x180035a20  mov     rdi, rcx
0x180035a23  mov     rbx, rdx
0x180035a26  mov     edx, 10h; void *
0x180035a2b  lea     rcx, [r8+10h]; this
0x180035a2f  mov     r13, r8
0x180035a32  call    ?_HashBytes@utl@@YA_KPEBX_K@Z; utl::_HashBytes(void const *,unsigned __int64)
0x180035a37  mov     rdx, [rdi+90h]
0x180035a3e  mov     rsi, rax
0x180035a41  mov     rcx, [rdi+8]
0x180035a45  and     esi, 1Fh
0x180035a48  mov     r10d, [rcx+rsi*4]
0x180035a4c  mov     [rbp+var_50], r10d
0x180035a50  mov     eax, [rdx+20h]
0x180035a53  sub     eax, [rdx+18h]
0x180035a56  mov     r8d, eax; unsigned int
0x180035a59  add     eax, 0FFFFFFFCh
0x180035a5c  cmp     r10d, eax
0x180035a5f  jnb     loc_180035B66
0x180035a65  mov     rdx, [rdx+18h]; unsigned __int8 *
0x180035a69  mov     ecx, r10d; unsigned int
0x180035a6c  call    ?LoopExists@@YA_NKPEBEK@Z; LoopExists(ulong,uchar const *,ulong)
0x180035a71  test    al, al
0x180035a73  jnz     loc_180035B66
0x180035a79  jmp     short loc_180035AEE
0x180035a7b  mov     rcx, [rdi+90h]
0x180035a82  mov     r14d, r10d
0x180035a85  mov     [rbp+var_40], 0
0x180035a8c  mov     rax, [rcx+18h]
0x180035a90  add     r14, rax
0x180035a93  mov     [rbp+var_48], rax
0x180035a97  mov     eax, [rcx+20h]
0x180035a9a  mov     edx, r14d
0x180035a9d  sub     edx, [rcx+18h]
0x180035aa0  sub     eax, [rcx+18h]
0x180035aa3  add     edx, 4; unsigned int
0x180035aa6  lea     rcx, [rbp+var_48]; this
0x180035aaa  mov     [rbp+var_3C], eax
0x180035aad  call    ?Advance@UserBuffer@@QEAAXK@Z; UserBuffer::Advance(ulong)
0x180035ab2  xorps   xmm0, xmm0
0x180035ab5  lea     rdx, [rbp+var_48]; struct UserBuffer *
0x180035ab9  xorps   xmm1, xmm1
0x180035abc  lea     rcx, [rbp+pExceptionObject]; this
0x180035ac0  movdqu  [rbp+pExceptionObject], xmm0
0x180035ac5  movups  [rbp+var_28], xmm0
0x180035ac9  movdqu  [rbp+var_18], xmm1
0x180035ace  call    ?Deserialize@BinXmlTemplate@@QEAAXAEAVUserBuffer@@@Z; BinXmlTemplate::Deserialize(UserBuffer &)
0x180035ad3  mov     rax, qword ptr [rbp+var_28]
0x180035ad7  cmp     rax, [r13+10h]
0x180035adb  jnz     short loc_180035AE7
0x180035add  mov     rax, qword ptr [rbp+var_28+8]
0x180035ae1  cmp     rax, [r13+18h]
0x180035ae5  jz      short loc_180035B52
0x180035ae7  mov     r10d, [r14]
0x180035aea  mov     [rbp+var_50], r10d
0x180035aee  test    r10d, r10d
0x180035af1  jnz     short loc_180035A7B
0x180035af3  mov     eax, [rbx+10h]
0x180035af6  lea     r8d, [r10+4]; unsigned int
0x180035afa  add     eax, 4
0x180035afd  lea     rdx, [rbp+var_4C]; void *
0x180035b01  mov     rcx, rbx; this
0x180035b04  mov     [rbp+var_4C], eax
0x180035b07  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180035b0c  mov     rax, [rdi+8]
0x180035b10  mov     r8d, 4; unsigned int
0x180035b16  mov     rcx, rbx; this
0x180035b19  lea     rdx, [rax+rsi*4]; void *
0x180035b1d  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180035b22  mov     rdx, [rdi+8]
0x180035b26  mov     rcx, r13; this
0x180035b29  mov     eax, [rbp+var_4C]
0x180035b2c  mov     [rdx+rsi*4], eax
0x180035b2f  mov     rdx, rbx; struct WriteBuffer *
0x180035b32  call    ?Serialize@BinXmlTemplate@@QEBAXAEAVWriteBuffer@@_N@Z; BinXmlTemplate::Serialize(WriteBuffer &,bool)
0x180035b37  mov     rcx, [rbp+var_8]
0x180035b3b  xor     rcx, rsp; StackCookie
0x180035b3e  call    __security_check_cookie
0x180035b43  add     rsp, 70h
0x180035b47  pop     r15
0x180035b49  pop     r14
0x180035b4b  pop     r13
0x180035b4d  pop     rdi
0x180035b4e  pop     rsi
0x180035b4f  pop     rbx
0x180035b50  pop     rbp
0x180035b51  retn
0x180035b52  mov     r8d, 4; unsigned int
0x180035b58  lea     rdx, [rbp+var_50]; void *
0x180035b5c  mov     rcx, rbx; this
0x180035b5f  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180035b64  jmp     short loc_180035B37
0x180035b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b6d  lea     rax, WPP_GLOBAL_Control
0x180035b74  mov     ebx, 0Dh
0x180035b79  cmp     rcx, rax
0x180035b7c  jz      short loc_180035BA3
0x180035b7e  test    dword ptr [rcx+1Ch], 200h
0x180035b85  jz      short loc_180035BA3
0x180035b87  cmp     byte ptr [rcx+19h], 2
0x180035b8b  jb      short loc_180035BA3
0x180035b8d  mov     rcx, [rcx+10h]
0x180035b91  lea     edx, [rbx-3]
0x180035b94  mov     r9d, ebx
0x180035b97  lea     r8, WPP_b0a585e5e25b3fab73f596ff3bcfdc94_Traceguids
0x180035b9e  call    WPP_SF_D
0x180035ba3  mov     r9d, 23h ; '#'; int
0x180035ba9  lea     rcx, [rbp+pExceptionObject]; this
0x180035bad  mov     edx, ebx; unsigned int
0x180035baf  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x180035bb4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180035bbb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035bbf  call    _CxxThrowException_0
```
