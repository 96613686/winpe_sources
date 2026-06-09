# SAXWriter::xout_attribute(wchar_t const *,int,wchar_t const *,int)

- ea: `0x10041c2d0`
- end: `0x10041c3e3`
- name: `?xout_attribute@SAXWriter@@MEAAXPEB_WH0H@Z`
- size: `275`
- prototype: `void __fastcall(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x10041c2d0`
- `0x100421f10`
- `0x1004228c0`
- `0x100422990`
- `0x100422b70`

## pseudocode

```c
void __fastcall SAXWriter::xout_attribute(SAXWriter *this, const wchar_t *a2, int a3, const wchar_t *a4, int a5)
{
  __int64 v5; // rbx

  v5 = *((_QWORD *)this + 13);
  if ( *(_DWORD *)(v5 + 48) )
    OutputHelper::_actuallyWriteWS(*((OutputHelper **)this + 13));
  **(_WORD **)(v5 + 24) = 32;
  *(_QWORD *)(v5 + 24) += 2LL;
  if ( *(_QWORD *)(v5 + 24) >= *(_QWORD *)(v5 + 32) )
    OutputHelper::_hardWrite((OutputHelper *)v5);
  OutputHelper::write((OutputHelper *)v5, a2, a3);
  if ( *(_DWORD *)(v5 + 48) )
    OutputHelper::_actuallyWriteWS((OutputHelper *)v5);
  **(_WORD **)(v5 + 24) = 61;
  *(_QWORD *)(v5 + 24) += 2LL;
  if ( *(_QWORD *)(v5 + 24) >= *(_QWORD *)(v5 + 32) )
    OutputHelper::_hardWrite((OutputHelper *)v5);
  if ( *(_DWORD *)(v5 + 48) )
    OutputHelper::_actuallyWriteWS((OutputHelper *)v5);
  **(_WORD **)(v5 + 24) = 34;
  *(_QWORD *)(v5 + 24) += 2LL;
  if ( *(_QWORD *)(v5 + 24) >= *(_QWORD *)(v5 + 32) )
    OutputHelper::_hardWrite((OutputHelper *)v5);
  XMLOutputHelper::canonical_attributeText((XMLOutputHelper *)v5, a4, a5);
  if ( *(_DWORD *)(v5 + 48) )
    OutputHelper::_actuallyWriteWS((OutputHelper *)v5);
  **(_WORD **)(v5 + 24) = 34;
  *(_QWORD *)(v5 + 24) += 2LL;
  if ( *(_QWORD *)(v5 + 24) >= *(_QWORD *)(v5 + 32) )
    OutputHelper::_hardWrite((OutputHelper *)v5);
}

```

## disassembly

```asm
0x10041c2d0  mov     [rsp+arg_0], rbx
0x10041c2d5  mov     [rsp+arg_8], rbp
0x10041c2da  mov     [rsp+arg_10], rsi
0x10041c2df  push    rdi
0x10041c2e0  sub     rsp, 20h
0x10041c2e4  mov     rbx, [rcx+68h]
0x10041c2e8  mov     rbp, r9
0x10041c2eb  mov     edi, r8d
0x10041c2ee  mov     rsi, rdx
0x10041c2f1  cmp     dword ptr [rbx+30h], 0
0x10041c2f5  jz      short loc_10041C2FF
0x10041c2f7  mov     rcx, rbx; this
0x10041c2fa  call    ?_actuallyWriteWS@OutputHelper@@IEAAXXZ; OutputHelper::_actuallyWriteWS(void)
0x10041c2ff  mov     rax, [rbx+18h]
0x10041c303  mov     ecx, 20h ; ' '
0x10041c308  mov     [rax], cx
0x10041c30b  add     qword ptr [rbx+18h], 2
0x10041c310  mov     rax, [rbx+18h]
0x10041c314  cmp     rax, [rbx+20h]
0x10041c318  jb      short loc_10041C322
0x10041c31a  mov     rcx, rbx; this
0x10041c31d  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10041c322  mov     r8d, edi; int
0x10041c325  mov     rdx, rsi; wchar_t *
0x10041c328  mov     rcx, rbx; this
0x10041c32b  call    ?write@OutputHelper@@QEAAXPEB_WH@Z; OutputHelper::write(wchar_t const *,int)
0x10041c330  cmp     dword ptr [rbx+30h], 0
0x10041c334  jz      short loc_10041C33E
0x10041c336  mov     rcx, rbx; this
0x10041c339  call    ?_actuallyWriteWS@OutputHelper@@IEAAXXZ; OutputHelper::_actuallyWriteWS(void)
0x10041c33e  mov     rax, [rbx+18h]
0x10041c342  mov     ecx, 3Dh ; '='
0x10041c347  mov     [rax], cx
0x10041c34a  add     qword ptr [rbx+18h], 2
0x10041c34f  mov     rax, [rbx+18h]
0x10041c353  cmp     rax, [rbx+20h]
0x10041c357  jb      short loc_10041C361
0x10041c359  mov     rcx, rbx; this
0x10041c35c  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10041c361  cmp     dword ptr [rbx+30h], 0
0x10041c365  jz      short loc_10041C36F
0x10041c367  mov     rcx, rbx; this
0x10041c36a  call    ?_actuallyWriteWS@OutputHelper@@IEAAXXZ; OutputHelper::_actuallyWriteWS(void)
0x10041c36f  mov     rax, [rbx+18h]
0x10041c373  mov     edi, 22h ; '"'
0x10041c378  mov     [rax], di
0x10041c37b  add     qword ptr [rbx+18h], 2
0x10041c380  mov     rax, [rbx+18h]
0x10041c384  cmp     rax, [rbx+20h]
0x10041c388  jb      short loc_10041C392
0x10041c38a  mov     rcx, rbx; this
0x10041c38d  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10041c392  mov     r8d, [rsp+28h+arg_20]; int
0x10041c397  mov     rdx, rbp; wchar_t *
0x10041c39a  mov     rcx, rbx; this
0x10041c39d  call    ?canonical_attributeText@XMLOutputHelper@@IEAAXPEB_WH@Z; XMLOutputHelper::canonical_attributeText(wchar_t const *,int)
0x10041c3a2  cmp     dword ptr [rbx+30h], 0
0x10041c3a6  jz      short loc_10041C3B0
0x10041c3a8  mov     rcx, rbx; this
0x10041c3ab  call    ?_actuallyWriteWS@OutputHelper@@IEAAXXZ; OutputHelper::_actuallyWriteWS(void)
0x10041c3b0  mov     rax, [rbx+18h]
0x10041c3b4  mov     [rax], di
0x10041c3b7  add     qword ptr [rbx+18h], 2
0x10041c3bc  mov     rax, [rbx+18h]
0x10041c3c0  cmp     rax, [rbx+20h]
0x10041c3c4  jb      short loc_10041C3CE
0x10041c3c6  mov     rcx, rbx; this
0x10041c3c9  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10041c3ce  mov     rbx, [rsp+28h+arg_0]
0x10041c3d3  mov     rbp, [rsp+28h+arg_8]
0x10041c3d8  mov     rsi, [rsp+28h+arg_10]
0x10041c3dd  add     rsp, 20h
0x10041c3e1  pop     rdi
0x10041c3e2  retn
```
