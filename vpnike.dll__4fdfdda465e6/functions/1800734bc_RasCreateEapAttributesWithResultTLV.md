# RasCreateEapAttributesWithResultTLV

- ea: `0x1800734bc`
- end: `0x180073651`
- name: `RasCreateEapAttributesWithResultTLV`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180073f1c`

## callees

- `0x1800734bc`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073538`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007354b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073538`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007354b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073560`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073560`

## string_xrefs

- `0x18007350b`: `RasCreateEapAttributesWithResultTLV -- Entering.`
- `0x1800735dd`: `RasCreateEapAttributesWithResultTLV: Constructed a response attribute.`
- `0x18007357b`: `RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.`
- `0x1800735fb`: `RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.`

## pseudocode

```c
__int64 __fastcall RasCreateEapAttributesWithResultTLV(__int64 a1, __int16 a2)
{
  unsigned int v4; // ebx
  _DWORD *v5; // rdi
  _BYTE *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v11[2044]; // [rsp+24h] [rbp-834h] BYREF

  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( *((_QWORD *)&xmmword_1800AB2C0 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_1800AB2C0 + 1),
      L"RasCreateEapAttributesWithResultTLV -- Entering.");
  if ( !a1 )
  {
    v4 = 87;
    goto LABEL_9;
  }
  *(_OWORD *)a1 = 0;
  v5 = LocalAlloc(0x40u, 0x10u);
  if ( !v5 )
  {
LABEL_8:
    v4 = 8;
LABEL_9:
    if ( (_QWORD)xmmword_1800AB2C0 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.", v4);
      v7 = xmmword_1800AB2C0;
LABEL_14:
      ((void (__fastcall *)(__int64, __int64, int *))gRasEapTemplateFunc)(gRasEapEtwContext, v7, &v10);
      return v4;
    }
    return v4;
  }
  v6 = LocalAlloc(0x40u, 6u);
  *((_QWORD *)v5 + 1) = v6;
  if ( !v6 )
  {
    LocalFree(v5);
    goto LABEL_8;
  }
  *v5 = 8102;
  v4 = 0;
  v5[1] = 6;
  *(_DWORD *)v6 = 33555328;
  v6[4] = HIBYTE(a2);
  v6[5] = a2;
  v8 = *((_QWORD *)&xmmword_1800AB2C0 + 1);
  *(_DWORD *)a1 = 1;
  *(_QWORD *)(a1 + 8) = v5;
  if ( v8 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      v8,
      L"RasCreateEapAttributesWithResultTLV: Constructed a response attribute.");
    if ( *((_QWORD *)&xmmword_1800AB2C0 + 1) )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"RasCreateEapAttributesWithResultTLV: Leaving -- 0x%x.", 0);
      v7 = *((_QWORD *)&xmmword_1800AB2C0 + 1);
      goto LABEL_14;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800734bc  push    rbx
0x1800734be  push    rbp
0x1800734bf  push    rsi
0x1800734c0  push    rdi
0x1800734c1  sub     rsp, 838h
0x1800734c8  mov     rax, cs:__security_cookie
0x1800734cf  xor     rax, rsp
0x1800734d2  mov     [rsp+858h+var_38], rax
0x1800734da  movzx   ebp, dx
0x1800734dd  mov     rsi, rcx
0x1800734e0  xor     eax, eax
0x1800734e2  lea     rcx, [rsp+858h+var_834]; void *
0x1800734e7  xor     edx, edx; Val
0x1800734e9  mov     [rsp+858h+var_838], eax
0x1800734ed  mov     r8d, 7FCh; Size
0x1800734f3  call    memset_0
0x1800734f8  mov     rdx, qword ptr cs:xmmword_1800AB2C0+8
0x1800734ff  test    rdx, rdx
0x180073502  jz      short loc_18007351E
0x180073504  mov     rcx, cs:gRasEapEtwContext
0x18007350b  lea     r8, aRascreateeapat_2; "RasCreateEapAttributesWithResultTLV -- "...
0x180073512  mov     rax, cs:gRasEapTemplateFunc
0x180073519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007351e  test    rsi, rsi
0x180073521  jnz     short loc_180073528
0x180073523  lea     ebx, [rsi+57h]
0x180073526  jmp     short loc_18007356B
0x180073528  mov     edx, 10h; uBytes
0x18007352d  xorps   xmm0, xmm0
0x180073530  movups  xmmword ptr [rsi], xmm0
0x180073533  lea     ebx, [rdx+30h]
0x180073536  mov     ecx, ebx; uFlags
0x180073538  call    cs:__imp_LocalAlloc
0x18007353e  mov     rdi, rax
0x180073541  test    rax, rax
0x180073544  jz      short loc_180073566
0x180073546  lea     edx, [rbx-3Ah]; uBytes
0x180073549  mov     ecx, ebx; uFlags
0x18007354b  call    cs:__imp_LocalAlloc
0x180073551  mov     [rdi+8], rax
0x180073555  mov     rcx, rax
0x180073558  test    rax, rax
0x18007355b  jnz     short loc_18007359D
0x18007355d  mov     rcx, rdi; hMem
0x180073560  call    cs:__imp_LocalFree
0x180073566  mov     ebx, 8
0x18007356b  cmp     qword ptr cs:xmmword_1800AB2C0, 0
0x180073573  jz      loc_180073633
0x180073579  xor     eax, eax
0x18007357b  lea     rdx, aRascreateeapat_0; "RasCreateEapAttributesWithResultTLV: Le"...
0x180073582  mov     r8d, ebx
0x180073585  mov     word ptr [rsp+858h+var_838], ax
0x18007358a  lea     rcx, [rsp+858h+var_838]
0x18007358f  call    FormatRRASErrorString
0x180073594  mov     rdx, qword ptr cs:xmmword_1800AB2C0
0x18007359b  jmp     short loc_18007361B
0x18007359d  mov     dword ptr [rdi], 1FA6h
0x1800735a3  xor     ebx, ebx
0x1800735a5  mov     dword ptr [rdi+4], 6
0x1800735ac  mov     dword ptr [rax], 2000380h
0x1800735b2  movzx   eax, bp
0x1800735b5  shr     ax, 8
0x1800735b9  mov     [rcx+4], al
0x1800735bc  mov     [rcx+5], bpl
0x1800735c0  mov     rdx, qword ptr cs:xmmword_1800AB2C0+8
0x1800735c7  mov     dword ptr [rsi], 1
0x1800735cd  mov     [rsi+8], rdi
0x1800735d1  test    rdx, rdx
0x1800735d4  jz      short loc_180073633
0x1800735d6  mov     rcx, cs:gRasEapEtwContext
0x1800735dd  lea     r8, aRascreateeapat_1; "RasCreateEapAttributesWithResultTLV: Co"...
0x1800735e4  mov     rax, cs:gRasEapTemplateFunc
0x1800735eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800735f0  cmp     qword ptr cs:xmmword_1800AB2C0+8, rbx
0x1800735f7  jz      short loc_180073633
0x1800735f9  xor     eax, eax
0x1800735fb  lea     rdx, aRascreateeapat_0; "RasCreateEapAttributesWithResultTLV: Le"...
0x180073602  xor     r8d, r8d
0x180073605  mov     word ptr [rsp+858h+var_838], ax
0x18007360a  lea     rcx, [rsp+858h+var_838]
0x18007360f  call    FormatRRASErrorString
0x180073614  mov     rdx, qword ptr cs:xmmword_1800AB2C0+8
0x18007361b  mov     rcx, cs:gRasEapEtwContext
0x180073622  lea     r8, [rsp+858h+var_838]
0x180073627  mov     rax, cs:gRasEapTemplateFunc
0x18007362e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073633  mov     eax, ebx
0x180073635  mov     rcx, [rsp+858h+var_38]
0x18007363d  xor     rcx, rsp; StackCookie
0x180073640  call    __security_check_cookie
0x180073645  add     rsp, 838h
0x18007364c  pop     rdi
0x18007364d  pop     rsi
0x18007364e  pop     rbp
0x18007364f  pop     rbx
0x180073650  retn
```
