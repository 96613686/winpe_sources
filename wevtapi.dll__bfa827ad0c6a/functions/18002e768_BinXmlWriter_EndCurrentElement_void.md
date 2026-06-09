# BinXmlWriter::EndCurrentElement(void)

- ea: `0x18002e768`
- end: `0x18002e8f9`
- name: `?EndCurrentElement@BinXmlWriter@@AEAAXXZ`
- size: `401`
- prototype: `void __fastcall(BinXmlWriter *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002e6c4`
- `0x18002e900`

## callees

- `0x18000314c`
- `0x180003780`
- `0x180008b20`
- `0x180023548`
- `0x18002e768`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlWriter::EndCurrentElement(BinXmlWriter *this)
{
  __int64 v2; // r8
  unsigned int v3; // esi
  _QWORD *v4; // rdx
  WriteBuffer *v5; // rcx
  unsigned int v6; // ebx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+38h] [rbp-20h]
  int v10; // [rsp+3Ch] [rbp-1Ch]
  int v11; // [rsp+40h] [rbp-18h]
  int v12; // [rsp+80h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 7);
  if ( *((_QWORD *)this + 6) == v2 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 13);
    }
    v9 = 13;
    v10 = -1;
    v8 = 0;
    v11 = 512;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v3 = *(_DWORD *)(v2 - 8) + (*((_BYTE *)this + 105) != 0 ? 3 : 1);
  utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::pop_back((char *)this + 48);
  if ( v3 > 0x7FFFFFFF )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 13);
    }
    v9 = 13;
    v10 = -1;
    v8 = 0;
    v11 = 526;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_DWORD *)this + 20) && *((_DWORD *)this + 21) && (*v4 == v4[1] || !*(_BYTE *)(*((_QWORD *)this + 7) - 4LL)) )
  {
    WriteBuffer::SetCurrentIndex(*(WriteBuffer **)this, *((_DWORD *)this + 20));
    if ( *((_DWORD *)this + 21) != -1 )
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + *((unsigned int *)this + 21)) &= ~0x40u;
  }
  v5 = *(WriteBuffer **)this;
  *((_QWORD *)this + 10) = 0;
  v12 = *((_DWORD *)v5 + 4) - v3 - 3;
  v6 = *((_DWORD *)v5 + 4);
  WriteBuffer::SetCurrentIndex(v5, v3);
  WriteBuffer::Write(*(WriteBuffer **)this, &v12, 4u);
  WriteBuffer::SetCurrentIndex(*(WriteBuffer **)this, v6);
}

```

## disassembly

```asm
0x18002e768  push    rbp
0x18002e76a  push    rbx
0x18002e76b  push    rsi
0x18002e76c  push    rdi
0x18002e76d  mov     rbp, rsp
0x18002e770  sub     rsp, 58h
0x18002e774  lea     rdx, [rcx+30h]
0x18002e778  mov     rdi, rcx
0x18002e77b  mov     r8, [rdx+8]
0x18002e77f  cmp     [rdx], r8
0x18002e782  jnz     short loc_18002E7EE
0x18002e784  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e78b  lea     rax, WPP_GLOBAL_Control
0x18002e792  mov     edi, 0Dh
0x18002e797  cmp     rcx, rax
0x18002e79a  jz      short loc_18002E7BE
0x18002e79c  test    byte ptr [rcx+1Ch], 2
0x18002e7a0  jz      short loc_18002E7BE
0x18002e7a2  cmp     byte ptr [rcx+19h], 2
0x18002e7a6  jb      short loc_18002E7BE
0x18002e7a8  mov     rcx, [rcx+10h]
0x18002e7ac  lea     edx, [rdi+5]
0x18002e7af  mov     r9d, edi
0x18002e7b2  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002e7b9  call    WPP_SF_D
0x18002e7be  xorps   xmm0, xmm0
0x18002e7c1  mov     [rbp+var_20], edi
0x18002e7c4  xor     ebx, ebx
0x18002e7c6  mov     [rbp+var_1C], 0FFFFFFFFh
0x18002e7cd  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002e7d4  mov     [rbp+var_28], rbx
0x18002e7d8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002e7dc  mov     [rbp+var_18], 200h
0x18002e7e3  movdqu  [rbp+pExceptionObject], xmm0
0x18002e7e8  call    _CxxThrowException_0
0x18002e7ee  mov     al, [rcx+69h]
0x18002e7f1  neg     al
0x18002e7f3  sbb     ecx, ecx
0x18002e7f5  and     ecx, 2
0x18002e7f8  lea     esi, [rcx+1]
0x18002e7fb  mov     rcx, rdx
0x18002e7fe  add     esi, [r8-8]
0x18002e802  call    ?pop_back@?$vector@UElementInfo@BinXmlWriter@@V?$allocator@UElementInfo@BinXmlWriter@@@utl@@@utl@@QEAAXXZ; utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::pop_back(void)
0x18002e807  cmp     esi, 7FFFFFFFh
0x18002e80d  jbe     short loc_18002E879
0x18002e80f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e816  lea     rax, WPP_GLOBAL_Control
0x18002e81d  mov     edi, 0Dh
0x18002e822  cmp     rcx, rax
0x18002e825  jz      short loc_18002E849
0x18002e827  test    byte ptr [rcx+1Ch], 2
0x18002e82b  jz      short loc_18002E849
0x18002e82d  cmp     byte ptr [rcx+19h], 2
0x18002e831  jb      short loc_18002E849
0x18002e833  mov     rcx, [rcx+10h]
0x18002e837  lea     edx, [rdi+6]
0x18002e83a  mov     r9d, edi
0x18002e83d  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002e844  call    WPP_SF_D
0x18002e849  xorps   xmm0, xmm0
0x18002e84c  mov     [rbp+var_20], edi
0x18002e84f  xor     ebx, ebx
0x18002e851  mov     [rbp+var_1C], 0FFFFFFFFh
0x18002e858  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002e85f  mov     [rbp+var_28], rbx
0x18002e863  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002e867  mov     [rbp+var_18], 20Eh
0x18002e86e  movdqu  [rbp+pExceptionObject], xmm0
0x18002e873  call    _CxxThrowException_0
0x18002e879  xor     ebx, ebx
0x18002e87b  cmp     [rdi+50h], ebx
0x18002e87e  jz      short loc_18002E8B8
0x18002e880  cmp     [rdi+54h], ebx
0x18002e883  jz      short loc_18002E8B8
0x18002e885  mov     rax, [rdx+8]
0x18002e889  cmp     [rdx], rax
0x18002e88c  jz      short loc_18002E897
0x18002e88e  mov     rax, [rdi+38h]
0x18002e892  cmp     [rax-4], bl
0x18002e895  jnz     short loc_18002E8B8
0x18002e897  mov     edx, [rdi+50h]; unsigned int
0x18002e89a  mov     rcx, [rdi]; this
0x18002e89d  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002e8a2  cmp     dword ptr [rdi+54h], 0FFFFFFFFh
0x18002e8a6  jz      short loc_18002E8B8
0x18002e8a8  mov     rax, [rdi]
0x18002e8ab  mov     r8d, [rdi+54h]
0x18002e8af  mov     rcx, [rax+8]
0x18002e8b3  and     byte ptr [rcx+r8], 0BFh
0x18002e8b8  mov     rcx, [rdi]; this
0x18002e8bb  mov     edx, esi; unsigned int
0x18002e8bd  mov     [rdi+50h], rbx
0x18002e8c1  mov     eax, [rcx+10h]
0x18002e8c4  sub     eax, esi
0x18002e8c6  sub     eax, 3
0x18002e8c9  mov     [rbp+arg_0], eax
0x18002e8cc  mov     ebx, [rcx+10h]
0x18002e8cf  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002e8d4  mov     rcx, [rdi]; this
0x18002e8d7  lea     rdx, [rbp+arg_0]; void *
0x18002e8db  mov     r8d, 4; unsigned int
0x18002e8e1  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002e8e6  mov     rcx, [rdi]; this
0x18002e8e9  mov     edx, ebx; unsigned int
0x18002e8eb  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002e8f0  add     rsp, 58h
0x18002e8f4  pop     rdi
0x18002e8f5  pop     rsi
0x18002e8f6  pop     rbx
0x18002e8f7  pop     rbp
0x18002e8f8  retn
```
