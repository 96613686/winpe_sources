# CLexSchemaDecoder::WriteBeginNode(IStream *,ushort)

- ea: `0x1800fe95c`
- end: `0x1800fea1c`
- name: `?WriteBeginNode@CLexSchemaDecoder@@AEAAJPEAUIStream@@G@Z`
- size: `192`
- prototype: `__int64 __fastcall(CLexSchemaDecoder *this, struct IStream *, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800fea24`

## callees

- `0x1800034b0`
- `0x18000416c`
- `0x1800fe6a8`
- `0x1800fe95c`
- `0x1800feadc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fe9f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fe9f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLexSchemaDecoder::WriteBeginNode(CLexSchemaDecoder *this, struct IStream *a2, unsigned __int16 a3)
{
  __int64 v3; // rbx
  int v6; // edi
  __int64 v7; // rdx
  void *v8; // rbx
  const wchar_t *v9; // r9
  int v11; // [rsp+28h] [rbp-120h]
  LPVOID pv; // [rsp+30h] [rbp-118h] BYREF
  wchar_t Buffer[104]; // [rsp+40h] [rbp-108h] BYREF

  v3 = a3;
  pv = 0;
  v6 = CLexSchemaDecoder::IdToName(this, a3, (unsigned __int16 **)&pv);
  if ( v6 >= 0 )
  {
    v7 = 5 * v3;
    v11 = v3;
    v8 = pv;
    v9 = L"Category";
    if ( *(_WORD *)(*((_QWORD *)this + 2) + 2 * v7 + 2) )
      v9 = L"Value";
    swprintf_s(Buffer, 0x64u, L"<%s name=\"%s\" ID=\"%u\">\n", v9, pv, v11);
    v6 = CLexSchemaDecoder::WriteString(a2, Buffer);
    CoTaskMemFree(v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800fe95c  push    rbx
0x1800fe95e  push    rbp
0x1800fe95f  push    rsi
0x1800fe960  push    rdi
0x1800fe961  push    r14
0x1800fe963  sub     rsp, 120h
0x1800fe96a  mov     rax, cs:__security_cookie
0x1800fe971  xor     rax, rsp
0x1800fe974  mov     [rsp+148h+var_38], rax
0x1800fe97c  movzx   ebx, r8w
0x1800fe980  mov     rbp, rdx
0x1800fe983  xor     r14d, r14d
0x1800fe986  lea     r8, [rsp+148h+pv]; unsigned __int16 **
0x1800fe98b  movzx   edx, bx; unsigned __int16
0x1800fe98e  mov     [rsp+148h+pv], r14
0x1800fe993  mov     rsi, rcx
0x1800fe996  call    ?IdToName@CLexSchemaDecoder@@QEAAJGPEAPEAG@Z; CLexSchemaDecoder::IdToName(ushort,ushort * *)
0x1800fe99b  mov     edi, eax
0x1800fe99d  test    eax, eax
0x1800fe99f  js      short loc_1800FE9FC
0x1800fe9a1  mov     rax, [rsi+10h]
0x1800fe9a5  lea     rdx, [rbx+rbx*4]
0x1800fe9a9  lea     rcx, aValue_0; "Value"
0x1800fe9b0  mov     [rsp+148h+var_120], ebx
0x1800fe9b4  mov     rbx, [rsp+148h+pv]
0x1800fe9b9  lea     r9, aCategory; "Category"
0x1800fe9c0  lea     r8, aSNameSIdU; "<%s name=\"%s\" ID=\"%u\">\n"
0x1800fe9c7  mov     [rsp+148h+var_128], rbx
0x1800fe9cc  cmp     [rax+rdx*2+2], r14w
0x1800fe9d2  lea     edx, [r14+64h]; BufferCount
0x1800fe9d6  cmovnz  r9, rcx
0x1800fe9da  lea     rcx, [rsp+148h+Buffer]; Buffer
0x1800fe9df  call    swprintf_s
0x1800fe9e4  lea     rdx, [rsp+148h+Buffer]; unsigned __int16 *
0x1800fe9e9  mov     rcx, rbp; struct IStream *
0x1800fe9ec  call    ?WriteString@CLexSchemaDecoder@@CAJPEAUIStream@@PEBG@Z; CLexSchemaDecoder::WriteString(IStream *,ushort const *)
0x1800fe9f1  mov     rcx, rbx; pv
0x1800fe9f4  mov     edi, eax
0x1800fe9f6  call    cs:__imp_CoTaskMemFree
0x1800fe9fc  mov     eax, edi
0x1800fe9fe  mov     rcx, [rsp+148h+var_38]
0x1800fea06  xor     rcx, rsp; StackCookie
0x1800fea09  call    __security_check_cookie
0x1800fea0e  add     rsp, 120h
0x1800fea15  pop     r14
0x1800fea17  pop     rdi
0x1800fea18  pop     rsi
0x1800fea19  pop     rbp
0x1800fea1a  pop     rbx
0x1800fea1b  retn
```
