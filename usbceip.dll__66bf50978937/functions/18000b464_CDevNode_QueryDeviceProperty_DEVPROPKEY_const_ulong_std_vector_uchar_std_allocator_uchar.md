# CDevNode::QueryDeviceProperty(_DEVPROPKEY const &,ulong &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18000b464`
- end: `0x18000b569`
- name: `?QueryDeviceProperty@CDevNode@@AEAAXAEBU_DEVPROPKEY@@AEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `261`
- prototype: `DWORD __fastcall(_QWORD *, __int64, __int64, __int64 *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180004388`
- `0x180006d2c`
- `0x18000ad38`
- `0x18000ad94`
- `0x18000adec`
- `0x18000ae48`

## callees

- `0x180002e6e`
- `0x180008020`
- `0x1800080c8`
- `0x18000b464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b53b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b53b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b545`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000b51a`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000b51a`

## pseudocode

```c
DWORD __fastcall CDevNode::QueryDeviceProperty(_QWORD *a1, __int64 a2, __int64 a3, __int64 *a4)
{
  unsigned int v5; // esi
  __int64 v6; // r9
  unsigned int v10; // eax
  __int64 v11; // rbp
  __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  __int64 v14; // rax
  size_t v15; // rdi
  DWORD result; // eax
  DWORD LastError; // eax
  unsigned int i; // [rsp+90h] [rbp+8h] BYREF

  v5 = 0;
  v6 = *a4;
  if ( a4[1] != v6 )
    a4[1] = v6;
  v10 = 0;
  for ( i = 0; ; v10 = i )
  {
    if ( v10 == v5 )
      goto LABEL_12;
    v11 = a4[1];
    v12 = *a4;
    v13 = v11 - *a4;
    v5 = v10;
    if ( v10 >= v13 )
    {
      if ( v10 <= v13 )
        goto LABEL_12;
      if ( v10 > (unsigned __int64)(a4[2] - v12) )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a4, v10);
        goto LABEL_12;
      }
      v15 = v10 - v13;
      memset_0((void *)a4[1], 0, v15);
      v14 = v15 + v11;
    }
    else
    {
      v14 = v10 + v12;
    }
    a4[1] = v14;
LABEL_12:
    result = DevObjGetDeviceProperty(*a1, a1 + 2, a2, a3, *a4, v5, &i, 0);
    if ( result )
      return result;
    if ( GetLastError() != 122 )
      break;
  }
  result = GetLastError();
  if ( result )
  {
    LastError = GetLastError();
    CException::ThrowException(LastError, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18000b464  push    rbx
0x18000b466  push    rbp
0x18000b467  push    rsi
0x18000b468  push    rdi
0x18000b469  push    r12
0x18000b46b  push    r13
0x18000b46d  push    r14
0x18000b46f  push    r15
0x18000b471  sub     rsp, 48h
0x18000b475  mov     rbx, r9
0x18000b478  xor     esi, esi
0x18000b47a  mov     r9, [r9]
0x18000b47d  mov     r12, r8
0x18000b480  mov     r13, rdx
0x18000b483  mov     r14, rcx
0x18000b486  cmp     [rbx+8], r9
0x18000b48a  jz      short loc_18000B490
0x18000b48c  mov     [rbx+8], r9
0x18000b490  xor     eax, eax
0x18000b492  mov     [rsp+88h+arg_0], eax
0x18000b499  cmp     eax, esi
0x18000b49b  jz      short loc_18000B4EC
0x18000b49d  mov     rbp, [rbx+8]
0x18000b4a1  mov     rdx, [rbx]
0x18000b4a4  mov     rcx, rbp
0x18000b4a7  sub     rcx, rdx
0x18000b4aa  mov     esi, eax
0x18000b4ac  mov     edi, eax
0x18000b4ae  cmp     rsi, rcx
0x18000b4b1  jnb     short loc_18000B4B9
0x18000b4b3  lea     rax, [rsi+rdx]
0x18000b4b7  jmp     short loc_18000B4E8
0x18000b4b9  jbe     short loc_18000B4EC
0x18000b4bb  mov     rax, [rbx+10h]
0x18000b4bf  sub     rax, rdx
0x18000b4c2  cmp     rdi, rax
0x18000b4c5  jbe     short loc_18000B4D4
0x18000b4c7  mov     rdx, rdi
0x18000b4ca  mov     rcx, rbx
0x18000b4cd  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000b4d2  jmp     short loc_18000B4EC
0x18000b4d4  sub     rdi, rcx
0x18000b4d7  xor     edx, edx; Val
0x18000b4d9  mov     r8, rdi; Size
0x18000b4dc  mov     rcx, rbp; void *
0x18000b4df  call    memset_0
0x18000b4e4  lea     rax, [rdi+rbp]
0x18000b4e8  mov     [rbx+8], rax
0x18000b4ec  mov     rcx, [r14]
0x18000b4ef  lea     rax, [rsp+88h+arg_0]
0x18000b4f7  mov     [rsp+88h+var_50], 0
0x18000b4ff  lea     rdx, [r14+10h]
0x18000b503  mov     [rsp+88h+var_58], rax
0x18000b508  mov     r9, r12
0x18000b50b  mov     rax, [rbx]
0x18000b50e  mov     r8, r13
0x18000b511  mov     [rsp+88h+var_60], esi
0x18000b515  mov     [rsp+88h+var_68], rax
0x18000b51a  call    cs:__imp_DevObjGetDeviceProperty
0x18000b520  test    eax, eax
0x18000b522  jnz     short loc_18000B558
0x18000b524  call    cs:__imp_GetLastError
0x18000b52a  cmp     eax, 7Ah ; 'z'
0x18000b52d  jnz     short loc_18000B53B
0x18000b52f  mov     eax, [rsp+88h+arg_0]
0x18000b536  jmp     loc_18000B499
0x18000b53b  call    cs:__imp_GetLastError
0x18000b541  test    eax, eax
0x18000b543  jz      short loc_18000B558
0x18000b545  call    cs:__imp_GetLastError
0x18000b54b  xor     r8d, r8d
0x18000b54e  xor     edx, edx
0x18000b550  mov     ecx, eax
0x18000b552  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000b558  add     rsp, 48h
0x18000b55c  pop     r15
0x18000b55e  pop     r14
0x18000b560  pop     r13
0x18000b562  pop     r12
0x18000b564  pop     rdi
0x18000b565  pop     rsi
0x18000b566  pop     rbp
0x18000b567  pop     rbx
0x18000b568  retn
```
