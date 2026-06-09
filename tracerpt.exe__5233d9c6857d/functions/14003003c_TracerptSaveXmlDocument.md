# TracerptSaveXmlDocument

- ea: `0x14003003c`
- end: `0x140030125`
- name: `TracerptSaveXmlDocument`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002fba4`

## callees

- `0x14003003c`
- `0x140041010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x140030069`
- `OLEAUT32!__imp_VariantInit` at `0x140030069`
- `OLEAUT32!__imp_VariantClear` at `0x1400300f6`
- `OLEAUT32!__imp_VariantClear` at `0x1400300f6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x140030093`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x140030093`

## pseudocode

```c
__int64 __fastcall TracerptSaveXmlDocument(__int64 a1, const WCHAR *a2)
{
  HRESULT v4; // ebx
  __int64 (__fastcall *v5)(__int64, __int128 *); // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  __int128 v8; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  IStream *ppstm; // [rsp+98h] [rbp+28h] BYREF

  ppstm = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = SHCreateStreamOnFileEx(a2, 0x1022u, 0x80u, 1, 0, &ppstm);
  if ( v4 >= 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(IStream *, GUID *, ULONG *))ppstm)(
           ppstm,
           &GUID_00000000_0000_0000_c000_000000000046,
           (ULONG *)&pvarg.cyVal);
    if ( v4 >= 0 )
    {
      pRecInfo = pvarg.pRecInfo;
      pvarg.vt = 13;
      v5 = *(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 528LL);
      v8 = *(_OWORD *)&pvarg.vt;
      v4 = v5(a1, &v8);
    }
  }
  VariantClear(&pvarg);
  if ( ppstm )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14003003c  mov     [rsp-8+arg_0], rbx
0x140030041  mov     [rsp-8+arg_8], rdi
0x140030046  push    rbp
0x140030047  mov     rbp, rsp
0x14003004a  sub     rsp, 70h
0x14003004e  xor     eax, eax
0x140030050  mov     rdi, rcx
0x140030053  xorps   xmm0, xmm0
0x140030056  mov     qword ptr [rbp+pvarg+10h], rax
0x14003005a  lea     rcx, [rbp+pvarg]; pvarg
0x14003005e  mov     [rbp+arg_18], rax
0x140030062  movups  xmmword ptr [rbp+pvarg], xmm0
0x140030066  mov     rbx, rdx
0x140030069  call    cs:__imp_VariantInit
0x14003006f  mov     r9d, 1; fCreate
0x140030075  lea     rax, [rbp+arg_18]
0x140030079  mov     [rsp+70h+ppstm], rax; ppstm
0x14003007e  mov     edx, 1022h; grfMode
0x140030083  mov     rcx, rbx; pszFile
0x140030086  mov     [rsp+70h+pstmTemplate], 0; pstmTemplate
0x14003008f  lea     r8d, [r9+7Fh]; dwAttributes
0x140030093  call    cs:__imp_SHCreateStreamOnFileEx
0x140030099  mov     ebx, eax
0x14003009b  test    eax, eax
0x14003009d  js      short loc_1400300F2
0x14003009f  mov     rcx, [rbp+arg_18]
0x1400300a3  lea     r8, [rbp+pvarg+8]
0x1400300a7  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1400300ae  mov     rax, [rcx]
0x1400300b1  mov     rax, [rax]
0x1400300b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400300b9  mov     ebx, eax
0x1400300bb  test    eax, eax
0x1400300bd  js      short loc_1400300F2
0x1400300bf  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1400300c4  lea     rdx, [rbp+var_20]
0x1400300c8  mov     eax, 0Dh
0x1400300cd  movsd   [rbp+var_10], xmm1
0x1400300d2  mov     word ptr [rbp+pvarg], ax
0x1400300d6  mov     rcx, rdi
0x1400300d9  mov     rax, [rdi]
0x1400300dc  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1400300e0  mov     rax, [rax+210h]
0x1400300e7  movaps  [rbp+var_20], xmm0
0x1400300eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400300f0  mov     ebx, eax
0x1400300f2  lea     rcx, [rbp+pvarg]; pvarg
0x1400300f6  call    cs:__imp_VariantClear
0x1400300fc  mov     rcx, [rbp+arg_18]
0x140030100  test    rcx, rcx
0x140030103  jz      short loc_140030111
0x140030105  mov     rax, [rcx]
0x140030108  mov     rax, [rax+10h]
0x14003010c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030111  lea     r11, [rsp+70h+var_s0]
0x140030116  mov     eax, ebx
0x140030118  mov     rbx, [r11+10h]
0x14003011c  mov     rdi, [r11+18h]
0x140030120  mov     rsp, r11
0x140030123  pop     rbp
0x140030124  retn
```
