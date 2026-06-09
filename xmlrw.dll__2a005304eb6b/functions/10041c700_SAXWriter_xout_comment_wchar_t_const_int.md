# SAXWriter::xout_comment(wchar_t const *,int)

- ea: `0x10041c700`
- end: `0x10041c7c3`
- name: `?xout_comment@SAXWriter@@MEAAXPEB_WH@Z`
- size: `195`
- prototype: `void __fastcall(SAXWriter *__hidden this, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10041c700`
- `0x1004216e0`
- `0x1004228c0`
- `0x100422b70`

## pseudocode

```c
void __fastcall SAXWriter::xout_comment(SAXWriter *this, const wchar_t *a2, int a3)
{
  __int64 v3; // rbx
  _WORD *v6; // rax
  __int64 v7; // rdx

  v3 = *((_QWORD *)this + 13);
  if ( *(_DWORD *)(v3 + 48) )
    OutputHelper::_actuallyWriteWS(*((OutputHelper **)this + 13));
  **(_QWORD **)(v3 + 24) = 0x2D002D0021003CLL;
  *(_QWORD *)(v3 + 24) += 8LL;
  if ( *(_QWORD *)(v3 + 24) >= *(_QWORD *)(v3 + 32) )
    OutputHelper::_hardWrite((OutputHelper *)v3);
  XMLOutputHelper::commentText((XMLOutputHelper *)v3, a2, a3);
  if ( *(_BYTE *)(v3 + 4337) )
  {
    v6 = *(_WORD **)(v3 + 24);
    if ( *(v6 - 1) == 45 )
    {
      *v6 = 32;
      *(_QWORD *)(v3 + 24) += 2LL;
    }
  }
  v7 = *(_QWORD *)(v3 + 24);
  *(_BYTE *)(v3 + 4337) = 0;
  *(_DWORD *)v7 = *(_DWORD *)L"-->";
  *(_WORD *)(v7 + 4) = asc_1004488B8[2];
  *(_QWORD *)(v3 + 24) += 6LL;
  if ( *(_QWORD *)(v3 + 24) >= *(_QWORD *)(v3 + 32) )
    OutputHelper::_hardWrite((OutputHelper *)v3);
}

```

## disassembly

```asm
0x10041c700  mov     [rsp+arg_0], rbx
0x10041c705  mov     [rsp+arg_8], rsi
0x10041c70a  push    rdi
0x10041c70b  sub     rsp, 20h
0x10041c70f  mov     rbx, [rcx+68h]
0x10041c713  mov     edi, r8d
0x10041c716  mov     rsi, rdx
0x10041c719  cmp     dword ptr [rbx+30h], 0
0x10041c71d  jz      short loc_10041C727
0x10041c71f  mov     rcx, rbx; this
0x10041c722  call    ?_actuallyWriteWS@OutputHelper@@IEAAXXZ; OutputHelper::_actuallyWriteWS(void)
0x10041c727  mov     rax, [rbx+18h]
0x10041c72b  mov     rcx, 2D002D0021003Ch
0x10041c735  mov     [rax], rcx
0x10041c738  add     qword ptr [rbx+18h], 8
0x10041c73d  mov     rax, [rbx+18h]
0x10041c741  cmp     rax, [rbx+20h]
0x10041c745  jb      short loc_10041C74F
0x10041c747  mov     rcx, rbx; this
0x10041c74a  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10041c74f  mov     r8d, edi; int
0x10041c752  mov     rdx, rsi; wchar_t *
0x10041c755  mov     rcx, rbx; this
0x10041c758  call    ?commentText@XMLOutputHelper@@QEAAXPEB_WH@Z; XMLOutputHelper::commentText(wchar_t const *,int)
0x10041c75d  cmp     byte ptr [rbx+10F1h], 0
0x10041c764  jz      short loc_10041C77E
0x10041c766  mov     rax, [rbx+18h]
0x10041c76a  cmp     word ptr [rax-2], 2Dh ; '-'
0x10041c76f  jnz     short loc_10041C77E
0x10041c771  mov     ecx, 20h ; ' '
0x10041c776  mov     [rax], cx
0x10041c779  add     qword ptr [rbx+18h], 2
0x10041c77e  mov     rdx, [rbx+18h]
0x10041c782  mov     byte ptr [rbx+10F1h], 0
0x10041c789  mov     eax, dword ptr cs:asc_1004488B8; "-->"
0x10041c78f  mov     [rdx], eax
0x10041c791  movzx   eax, word ptr cs:asc_1004488B8+4; ">"
0x10041c798  mov     [rdx+4], ax
0x10041c79c  add     qword ptr [rbx+18h], 6
0x10041c7a1  mov     rax, [rbx+18h]
0x10041c7a5  cmp     rax, [rbx+20h]
0x10041c7a9  jb      short loc_10041C7B3
0x10041c7ab  mov     rcx, rbx; this
0x10041c7ae  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10041c7b3  mov     rbx, [rsp+28h+arg_0]
0x10041c7b8  mov     rsi, [rsp+28h+arg_8]
0x10041c7bd  add     rsp, 20h
0x10041c7c1  pop     rdi
0x10041c7c2  retn
```
