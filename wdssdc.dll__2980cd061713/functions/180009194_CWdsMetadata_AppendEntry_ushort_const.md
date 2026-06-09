# CWdsMetadata::AppendEntry(ushort const *)

- ea: `0x180009194`
- end: `0x18000926f`
- name: `?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z`
- size: `219`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180005dac`
- `0x180008f70`
- `0x18000906c`
- `0x18000c4cc`

## callees

- `0x1800015d4`
- `0x180002670`
- `0x180008da0`
- `0x180009194`
- `0x180009990`
- `0x18000be44`
- `0x18000bec0`
- `0x18000c274`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::AppendEntry(CWdsMetadata *this, const unsigned __int16 *a2)
{
  char *v4; // rax
  char *v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8

  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    *(_QWORD *)(v4 + 36) = 0;
    *((_OWORD *)v4 + 3) = 0;
    *(_QWORD *)v4 = 0;
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_DWORD *)v4 + 8) = 0;
    v6 = CWdsMetadataEntry::Initialize((CWdsMetadataEntry *)v4, a2);
    if ( (unsigned int)ElValidateWin32_1(v6, v7, v8, 0x1077u)
      || (v6 = CWdsMetadata::AddEntry(this, (struct CWdsMetadataEntry *)v5),
          (unsigned int)ElValidateWin32_1(v6, v9, v10, 0x107Au)) )
    {
      CWdsMetadataEntry::Shutdown((CWdsMetadataEntry *)v5);
      CWdsMetadataValue::Shutdown((CWdsMetadataValue *)(v5 + 40));
      operator delete(v5);
    }
  }
  else
  {
    return 8;
  }
  return v6;
}

```

## disassembly

```asm
0x180009194  mov     [rsp+arg_0], rbx
0x180009199  mov     [rsp+arg_8], rsi
0x18000919e  push    rdi
0x18000919f  sub     rsp, 20h
0x1800091a3  mov     rdi, rdx
0x1800091a6  mov     rsi, rcx
0x1800091a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800091b0  mov     ecx, 40h ; '@'; unsigned __int64
0x1800091b5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800091ba  mov     rbx, rax
0x1800091bd  test    rax, rax
0x1800091c0  jz      loc_180009257
0x1800091c6  xorps   xmm0, xmm0
0x1800091c9  mov     qword ptr [rax+24h], 0
0x1800091d1  movups  xmmword ptr [rax+30h], xmm0
0x1800091d5  mov     rdx, rdi; unsigned __int16 *
0x1800091d8  mov     qword ptr [rax], 0
0x1800091df  mov     rcx, rax; this
0x1800091e2  mov     qword ptr [rax+8], 0
0x1800091ea  mov     qword ptr [rax+10h], 0
0x1800091f2  mov     qword ptr [rax+18h], 0
0x1800091fa  mov     dword ptr [rax+20h], 0
0x180009201  call    ?Initialize@CWdsMetadataEntry@@QEAAKPEBG@Z; CWdsMetadataEntry::Initialize(ushort const *)
0x180009206  mov     r9d, 1077h
0x18000920c  mov     ecx, eax
0x18000920e  mov     edi, eax
0x180009210  call    ElValidateWin32_1
0x180009215  test    eax, eax
0x180009217  jnz     short loc_180009237
0x180009219  mov     rdx, rbx; struct CWdsMetadataEntry *
0x18000921c  mov     rcx, rsi; this
0x18000921f  call    ?AddEntry@CWdsMetadata@@AEAAKPEAVCWdsMetadataEntry@@@Z; CWdsMetadata::AddEntry(CWdsMetadataEntry *)
0x180009224  mov     r9d, 107Ah
0x18000922a  mov     ecx, eax
0x18000922c  mov     edi, eax
0x18000922e  call    ElValidateWin32_1
0x180009233  test    eax, eax
0x180009235  jz      short loc_18000925C
0x180009237  mov     rcx, rbx; this
0x18000923a  call    ?Shutdown@CWdsMetadataEntry@@QEAAXXZ; CWdsMetadataEntry::Shutdown(void)
0x18000923f  lea     rcx, [rbx+28h]; this
0x180009243  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180009248  mov     edx, 40h ; '@'
0x18000924d  mov     rcx, rbx; Block
0x180009250  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009255  jmp     short loc_18000925C
0x180009257  mov     edi, 8
0x18000925c  mov     rbx, [rsp+28h+arg_0]
0x180009261  mov     eax, edi
0x180009263  mov     rsi, [rsp+28h+arg_8]
0x180009268  add     rsp, 20h
0x18000926c  pop     rdi
0x18000926d  retn
```
