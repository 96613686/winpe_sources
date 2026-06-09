# CWMFileSinkV1::CreateIndexer(CASFStreamPropertiesObject *,ulong)

- ea: `0x180008b5c`
- end: `0x180008c63`
- name: `?CreateIndexer@CWMFileSinkV1@@IEAAJPEAVCASFStreamPropertiesObject@@K@Z`
- size: `263`
- prototype: `int(CWMFileSinkV1 *__hidden this, struct CASFStreamPropertiesObject *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004ed0`
- `0x18000b780`

## callees

- `0x1800011a0`
- `0x180008b5c`
- `0x18000f0f0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::CreateIndexer(
        CWMFileSinkV1 *this,
        struct CASFStreamPropertiesObject *a2,
        unsigned int a3)
{
  __int64 v6; // rdi
  __int64 v7; // rsi
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // edi
  struct _GUID v11; // xmm6
  CWMPerStreamIndex *v12; // rax
  unsigned __int64 v13; // r9
  CWMPerStreamIndex *v14; // rcx
  __int64 v15; // rcx
  unsigned __int64 v16; // [rsp+20h] [rbp-58h]
  struct _GUID v17; // [rsp+30h] [rbp-48h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v6 = *((unsigned __int16 *)a2 + 52);
  if ( (unsigned __int16)(v6 - 1) > 0x3Eu )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v7 = *((unsigned __int16 *)a2 + 52);
    if ( *((_QWORD *)this + v6 + 921) )
    {
      _mm_lfence();
      v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + v6 + 921) + 8LL))(*((_QWORD *)this + v6 + 921));
      v9 = *((_QWORD *)this + (unsigned int)v6 + 921);
      v10 = v8;
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 88LL))(v9, a3);
    }
    else
    {
      v11 = *(struct _GUID *)((char *)a2 + 56);
      v12 = (CWMPerStreamIndex *)operator new(0x29B8u);
      if ( v12 )
      {
        v16 = *((_QWORD *)this + 31);
        v17 = v11;
        v14 = CWMPerStreamIndex::CWMPerStreamIndex(v12, v6, &v17, v13, v16, a3);
      }
      else
      {
        v14 = 0;
      }
      *((_QWORD *)this + *((unsigned __int16 *)this + 4196) + 985) = v14;
      v15 = *((_QWORD *)this + *((unsigned __int16 *)this + 4196) + 985);
      if ( v15 )
      {
        v10 = 0;
        *((_QWORD *)this + v7 + 921) = v15;
        ++*((_WORD *)this + 4196);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180008b5c  push    rbx
0x180008b5e  push    rbp
0x180008b5f  push    rsi
0x180008b60  push    rdi
0x180008b61  sub     rsp, 58h
0x180008b65  movaps  [rsp+78h+var_38], xmm6
0x180008b6a  mov     ebp, r8d
0x180008b6d  mov     rbx, rcx
0x180008b70  test    rdx, rdx
0x180008b73  jnz     short loc_180008B7F
0x180008b75  mov     eax, 80004003h
0x180008b7a  jmp     loc_180008C55
0x180008b7f  movzx   edi, word ptr [rdx+68h]
0x180008b83  lea     eax, [rdi-1]
0x180008b86  cmp     ax, 3Eh ; '>'
0x180008b8a  ja      loc_180008C4E
0x180008b90  cmp     qword ptr [rcx+rdi*8+1CC8h], 0
0x180008b99  mov     esi, edi
0x180008b9b  jz      short loc_180008BD1
0x180008b9d  lfence
0x180008ba0  mov     rcx, [rcx+rdi*8+1CC8h]
0x180008ba8  mov     rax, [rcx]
0x180008bab  mov     rax, [rax+8]
0x180008baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bb4  mov     rcx, [rbx+rsi*8+1CC8h]
0x180008bbc  mov     edi, eax
0x180008bbe  mov     rdx, [rcx]
0x180008bc1  mov     rax, [rdx+58h]
0x180008bc5  mov     edx, ebp
0x180008bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bcc  jmp     loc_180008C53
0x180008bd1  movups  xmm6, xmmword ptr [rdx+38h]
0x180008bd5  mov     ecx, 29B8h; Size
0x180008bda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008bdf  test    rax, rax
0x180008be2  jz      short loc_180008C0F
0x180008be4  mov     rcx, [rbx+0F8h]
0x180008beb  lea     r8, [rsp+78h+var_48]; struct _GUID *
0x180008bf0  mov     [rsp+78h+var_50], ebp; unsigned int
0x180008bf4  movzx   edx, di; unsigned __int16
0x180008bf7  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180008bfc  mov     rcx, rax; this
0x180008bff  movdqa  xmmword ptr [rsp+78h+var_48.Data1], xmm6
0x180008c05  call    ??0CWMPerStreamIndex@@QEAA@GU_GUID@@_K1K@Z; CWMPerStreamIndex::CWMPerStreamIndex(ushort,_GUID,unsigned __int64,unsigned __int64,ulong)
0x180008c0a  mov     rcx, rax
0x180008c0d  jmp     short loc_180008C11
0x180008c0f  xor     ecx, ecx
0x180008c11  movzx   eax, word ptr [rbx+20C8h]
0x180008c18  mov     [rbx+rax*8+1EC8h], rcx
0x180008c20  movzx   eax, word ptr [rbx+20C8h]
0x180008c27  mov     rcx, [rbx+rax*8+1EC8h]
0x180008c2f  test    rcx, rcx
0x180008c32  jnz     short loc_180008C3B
0x180008c34  mov     edi, 8007000Eh
0x180008c39  jmp     short loc_180008C53
0x180008c3b  xor     edi, edi
0x180008c3d  mov     [rbx+rsi*8+1CC8h], rcx
0x180008c45  inc     word ptr [rbx+20C8h]
0x180008c4c  jmp     short loc_180008C53
0x180008c4e  mov     edi, 80070057h
0x180008c53  mov     eax, edi
0x180008c55  movaps  xmm6, [rsp+78h+var_38]
0x180008c5a  add     rsp, 58h
0x180008c5e  pop     rdi
0x180008c5f  pop     rsi
0x180008c60  pop     rbp
0x180008c61  pop     rbx
0x180008c62  retn
```
