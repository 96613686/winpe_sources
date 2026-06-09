# CDevNodeCollection::GetNextDevNode(std::unique_ptr<CDevNode,std::default_delete<CDevNode>> &)

- ea: `0x180008290`
- end: `0x180008510`
- name: `?GetNextDevNode@CDevNodeCollection@@QEAAEAEAV?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@@Z`
- size: `640`
- prototype: `char __fastcall(_QWORD *, __int64 *)`
- caller_count: `6`
- callee_count: `12`
- tags: ``

## callers

- `0x180003cf4`
- `0x180004388`
- `0x180005314`
- `0x180005a48`
- `0x180006d2c`
- `0x180007b44`

## callees

- `0x180002410`
- `0x18000246c`
- `0x180002e6e`
- `0x180003c6c`
- `0x180003cc4`
- `0x180004060`
- `0x1800040cc`
- `0x180008020`
- `0x1800080c8`
- `0x180008290`
- `0x180008518`
- `0x18000ae48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000832c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000833d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000832c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000833d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008499`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180008322`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180008322`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800083d6`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800083d6`

## pseudocode

```c
char __fastcall CDevNodeCollection::GetNextDevNode(_QWORD *a1, __int64 *a2)
{
  unsigned int v4; // r15d
  _DWORD *v5; // rdi
  char v6; // r14
  char *v7; // r12
  char *v8; // rax
  size_t v9; // rbx
  _QWORD *v10; // rbx
  __int64 v11; // rdx
  DWORD LastError; // eax
  DWORD v13; // eax
  __int64 v14; // rdx
  unsigned int v16; // [rsp+30h] [rbp-69h] BYREF
  _QWORD *v17; // [rsp+38h] [rbp-61h] BYREF
  char *v18; // [rsp+40h] [rbp-59h] BYREF
  void *v19; // [rsp+48h] [rbp-51h]
  __int64 v20; // [rsp+50h] [rbp-49h]
  _QWORD *v21; // [rsp+58h] [rbp-41h]
  __int128 v22; // [rsp+60h] [rbp-39h] BYREF
  __int128 v23; // [rsp+70h] [rbp-29h]
  __int128 v24; // [rsp+80h] [rbp-19h] BYREF
  __int128 v25; // [rsp+90h] [rbp-9h]
  __int128 v26; // [rsp+A0h] [rbp+7h]

  std::vector<_bstr_t>::vector<_bstr_t>(&v18);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v22 = 0;
  v23 = 0;
  v4 = 0;
  v16 = 0;
  v5 = 0;
  if ( v19 != v18 )
    v19 = v18;
  v6 = 1;
  while ( 2 )
  {
    LODWORD(v24) = 48;
    LODWORD(v22) = 32;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(*a1, 0, a1[2], *((unsigned int *)a1 + 3), &v22) )
    {
      if ( GetLastError() == 259 )
      {
        v6 = 0;
        goto LABEL_28;
      }
      if ( GetLastError() )
      {
        LastError = GetLastError();
        CException::ThrowException(LastError, 0, 0);
      }
    }
    ++*((_DWORD *)a1 + 3);
    do
    {
      if ( v16 == v4 )
        goto LABEL_17;
      v4 = v16;
      v7 = (char *)v19;
      v5 = v18;
      if ( v16 < (unsigned __int64)((_BYTE *)v19 - v18) )
      {
        v8 = &v18[v16];
LABEL_15:
        v19 = v8;
        goto LABEL_16;
      }
      if ( v16 > (unsigned __int64)((_BYTE *)v19 - v18) )
      {
        if ( v16 <= (unsigned __int64)(v20 - (_QWORD)v18) )
        {
          v9 = v16 - ((_BYTE *)v19 - v18);
          memset_0(v19, 0, v9);
          v8 = &v7[v9];
          v5 = v18;
          goto LABEL_15;
        }
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v18, v16);
        v5 = v18;
      }
LABEL_16:
      *v5 = 8;
LABEL_17:
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(*a1, &v22, v5, v4, &v16, &v24) )
        goto LABEL_20;
    }
    while ( GetLastError() == 122 );
    if ( GetLastError() )
    {
      v13 = GetLastError();
      CException::ThrowException(v13, 0, 0);
    }
LABEL_20:
    v10 = operator new(0x68u);
    v21 = v10;
    v11 = a1[2];
    *v10 = *a1;
    v10[1] = v11;
    *((_OWORD *)v10 + 1) = v24;
    *((_OWORD *)v10 + 2) = v25;
    *((_OWORD *)v10 + 3) = v26;
    *((_OWORD *)v10 + 4) = v22;
    *((_OWORD *)v10 + 5) = v23;
    v10[12] = 0;
    CDevNode::GetProperty((CDevNode *)v10, &DEVPKEY_Device_InstanceId, (struct _bstr_t *)(v10 + 12));
    v17 = v10;
    if ( !(unsigned __int8)CDevNodeCollection::PassedFilterCriteria(a1, &v17) )
    {
      std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(&v17);
      continue;
    }
    break;
  }
  v17 = 0;
  v14 = *a2;
  *a2 = (__int64)v10;
  if ( v14 )
    std::default_delete<CDevNode>::operator()();
  std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(&v17);
LABEL_28:
  if ( v18 )
    std::_Deallocate<16>(v18, v20 - (_QWORD)v18);
  return v6;
}

```

## disassembly

```asm
0x180008290  mov     [rsp-8+arg_10], rbx
0x180008295  push    rbp
0x180008296  push    rsi
0x180008297  push    rdi
0x180008298  push    r12
0x18000829a  push    r13
0x18000829c  push    r14
0x18000829e  push    r15
0x1800082a0  lea     rbp, [rsp-27h]
0x1800082a5  sub     rsp, 0C0h
0x1800082ac  mov     rax, cs:__security_cookie
0x1800082b3  xor     rax, rsp
0x1800082b6  mov     [rbp+57h+var_40], rax
0x1800082ba  mov     r13, rdx
0x1800082bd  mov     rsi, rcx
0x1800082c0  lea     rcx, [rbp+57h+var_B0]
0x1800082c4  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x1800082c9  nop
0x1800082ca  xorps   xmm0, xmm0
0x1800082cd  movups  [rbp+57h+var_70], xmm0
0x1800082d1  movups  [rbp+57h+var_60], xmm0
0x1800082d5  movups  [rbp+57h+var_50], xmm0
0x1800082d9  movups  [rbp+57h+var_90], xmm0
0x1800082dd  movups  [rbp+57h+var_80], xmm0
0x1800082e1  xor     r15d, r15d
0x1800082e4  mov     [rbp+57h+var_C0], r15d
0x1800082e8  xor     edi, edi
0x1800082ea  mov     rcx, [rbp+57h+var_B0]
0x1800082ee  cmp     [rbp+57h+var_A8], rcx
0x1800082f2  jz      short loc_1800082F8
0x1800082f4  mov     [rbp+57h+var_A8], rcx
0x1800082f8  mov     r14d, 1
0x1800082fe  mov     dword ptr [rbp+57h+var_70], 30h ; '0'
0x180008305  mov     dword ptr [rbp+57h+var_90], 20h ; ' '
0x18000830c  lea     rax, [rbp+57h+var_90]
0x180008310  mov     [rsp+0F0h+var_D0], rax
0x180008315  mov     r9d, [rsi+0Ch]
0x180008319  mov     r8, [rsi+10h]
0x18000831d  xor     edx, edx
0x18000831f  mov     rcx, [rsi]
0x180008322  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180008328  test    eax, eax
0x18000832a  jnz     short loc_18000834B
0x18000832c  call    cs:__imp_GetLastError
0x180008332  cmp     eax, 103h
0x180008337  jz      loc_180008494
0x18000833d  call    cs:__imp_GetLastError
0x180008343  test    eax, eax
0x180008345  jnz     loc_180008481
0x18000834b  add     [rsi+0Ch], r14d
0x18000834f  cmp     [rbp+57h+var_C0], r15d
0x180008353  jz      short loc_1800083B7
0x180008355  mov     r15d, [rbp+57h+var_C0]
0x180008359  mov     ebx, r15d
0x18000835c  mov     r12, [rbp+57h+var_A8]
0x180008360  mov     rcx, r12
0x180008363  mov     rdi, [rbp+57h+var_B0]
0x180008367  sub     rcx, rdi
0x18000836a  cmp     r15, rcx
0x18000836d  jnb     short loc_180008375
0x18000836f  lea     rax, [r15+rdi]
0x180008373  jmp     short loc_1800083AD
0x180008375  jbe     short loc_1800083B1
0x180008377  mov     rax, [rbp+57h+var_A0]
0x18000837b  sub     rax, rdi
0x18000837e  cmp     rbx, rax
0x180008381  jbe     short loc_180008395
0x180008383  mov     rdx, rbx
0x180008386  lea     rcx, [rbp+57h+var_B0]
0x18000838a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000838f  mov     rdi, [rbp+57h+var_B0]
0x180008393  jmp     short loc_1800083B1
0x180008395  sub     rbx, rcx
0x180008398  mov     r8, rbx; Size
0x18000839b  xor     edx, edx; Val
0x18000839d  mov     rcx, r12; void *
0x1800083a0  call    memset_0
0x1800083a5  lea     rax, [rbx+r12]
0x1800083a9  mov     rdi, [rbp+57h+var_B0]
0x1800083ad  mov     [rbp+57h+var_A8], rax
0x1800083b1  mov     dword ptr [rdi], 8
0x1800083b7  lea     rax, [rbp+57h+var_70]
0x1800083bb  mov     [rsp+0F0h+var_C8], rax
0x1800083c0  lea     rax, [rbp+57h+var_C0]
0x1800083c4  mov     [rsp+0F0h+var_D0], rax
0x1800083c9  mov     r9d, r15d
0x1800083cc  mov     r8, rdi
0x1800083cf  lea     rdx, [rbp+57h+var_90]
0x1800083d3  mov     rcx, [rsi]
0x1800083d6  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800083dc  test    eax, eax
0x1800083de  jnz     short loc_1800083FD
0x1800083e0  call    cs:__imp_GetLastError
0x1800083e6  cmp     eax, 7Ah ; 'z'
0x1800083e9  jz      loc_18000834F
0x1800083ef  call    cs:__imp_GetLastError
0x1800083f5  test    eax, eax
0x1800083f7  jnz     loc_180008499
0x1800083fd  mov     ecx, 68h ; 'h'; Size
0x180008402  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008407  mov     rbx, rax
0x18000840a  mov     [rbp+57h+var_98], rax
0x18000840e  mov     rdx, [rsi+10h]
0x180008412  mov     rcx, [rsi]
0x180008415  mov     [rax], rcx
0x180008418  mov     [rax+8], rdx
0x18000841c  movups  xmm0, [rbp+57h+var_70]
0x180008420  movups  xmmword ptr [rax+10h], xmm0
0x180008424  movups  xmm1, [rbp+57h+var_60]
0x180008428  movups  xmmword ptr [rax+20h], xmm1
0x18000842c  movups  xmm0, [rbp+57h+var_50]
0x180008430  movups  xmmword ptr [rax+30h], xmm0
0x180008434  movups  xmm1, [rbp+57h+var_90]
0x180008438  movups  xmmword ptr [rax+40h], xmm1
0x18000843c  movups  xmm0, [rbp+57h+var_80]
0x180008440  movups  xmmword ptr [rax+50h], xmm0
0x180008444  lea     r8, [rax+60h]; struct _bstr_t *
0x180008448  mov     qword ptr [r8], 0
0x18000844f  lea     rdx, DEVPKEY_Device_InstanceId; struct _DEVPROPKEY *
0x180008456  mov     rcx, rax; this
0x180008459  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAV_bstr_t@@@Z; CDevNode::GetProperty(_DEVPROPKEY const &,_bstr_t &)
0x18000845e  nop
0x18000845f  mov     [rbp+57h+var_B8], rbx
0x180008463  lea     rdx, [rbp+57h+var_B8]
0x180008467  mov     rcx, rsi
0x18000846a  call    ?PassedFilterCriteria@CDevNodeCollection@@AEAAEAEAV?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@@Z; CDevNodeCollection::PassedFilterCriteria(std::unique_ptr<CDevNode> &)
0x18000846f  test    al, al
0x180008471  jnz     short loc_1800084AC
0x180008473  lea     rcx, [rbp+57h+var_B8]
0x180008477  call    ??1?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(void)
0x18000847c  jmp     loc_1800082FE
0x180008481  call    cs:__imp_GetLastError
0x180008487  mov     ecx, eax
0x180008489  xor     r8d, r8d
0x18000848c  xor     edx, edx
0x18000848e  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x180008494  xor     r14b, r14b
0x180008497  jmp     short loc_1800084D1
0x180008499  call    cs:__imp_GetLastError
0x18000849f  mov     ecx, eax
0x1800084a1  xor     r8d, r8d
0x1800084a4  xor     edx, edx
0x1800084a6  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x1800084ac  mov     [rbp+57h+var_B8], 0
0x1800084b4  mov     rdx, [r13+0]
0x1800084b8  mov     [r13+0], rbx
0x1800084bc  test    rdx, rdx
0x1800084bf  jz      short loc_1800084C7
0x1800084c1  call    ??R?$default_delete@VCDevNode@@@std@@QEBAXPEAVCDevNode@@@Z; std::default_delete<CDevNode>::operator()(CDevNode *)
0x1800084c6  nop
0x1800084c7  lea     rcx, [rbp+57h+var_B8]
0x1800084cb  call    ??1?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(void)
0x1800084d0  nop
0x1800084d1  mov     rcx, [rbp+57h+var_B0]
0x1800084d5  test    rcx, rcx
0x1800084d8  jz      short loc_1800084E6
0x1800084da  mov     rdx, [rbp+57h+var_A0]
0x1800084de  sub     rdx, rcx
0x1800084e1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800084e6  mov     al, r14b
0x1800084e9  mov     rcx, [rbp+57h+var_40]
0x1800084ed  xor     rcx, rsp; StackCookie
0x1800084f0  call    __security_check_cookie
0x1800084f5  mov     rbx, [rsp+0F0h+arg_10]
0x1800084fd  add     rsp, 0C0h
0x180008504  pop     r15
0x180008506  pop     r14
0x180008508  pop     r13
0x18000850a  pop     r12
0x18000850c  pop     rdi
0x18000850d  pop     rsi
0x18000850e  pop     rbp
0x18000850f  retn
```
