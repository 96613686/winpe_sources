# SdpFreeParamSet(_SDIAG_PARAMSET *)

- ea: `0x1800025c8`
- end: `0x180002699`
- name: `?SdpFreeParamSet@@YAJPEAU_SDIAG_PARAMSET@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(struct _SDIAG_PARAMSET *)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002554`
- `0x1800040e8`
- `0x1800183d0`
- `0x18001d420`
- `0x18001ed44`
- `0x180026474`

## callees

- `0x1800012a4`
- `0x1800025c8`
- `0x180026fa0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000261d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000264b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002666`
- `OLEAUT32!__imp_SysFreeString` at `0x18000261d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000264b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002666`

## pseudocode

```c
__int64 __fastcall SdpFreeParamSet(struct _SDIAG_PARAMSET *a1)
{
  unsigned int v2; // ebp
  __int64 i; // rsi
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx

  if ( a1 )
  {
    v2 = 0;
    if ( *(_QWORD *)a1 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 2); i = (unsigned int)(i + 1) )
      {
        v4 = *(OLECHAR **)(*(_QWORD *)a1 + 24 * i);
        if ( v4 )
        {
          SysFreeString(v4);
          *(_QWORD *)(*(_QWORD *)a1 + 24 * i) = 0;
        }
        if ( *(_QWORD *)(*(_QWORD *)a1 + 24 * i + 8) == *(_QWORD *)(*(_QWORD *)a1 + 24 * i + 16) )
          *(_QWORD *)(*(_QWORD *)a1 + 24 * i + 8) = 0;
        v5 = *(OLECHAR **)(*(_QWORD *)a1 + 24 * i + 8);
        if ( v5 )
        {
          SysFreeString(v5);
          *(_QWORD *)(*(_QWORD *)a1 + 24 * i + 8) = 0;
        }
        v6 = *(OLECHAR **)(*(_QWORD *)a1 + 24 * i + 16);
        if ( v6 )
        {
          SysFreeString(v6);
          *(_QWORD *)(*(_QWORD *)a1 + 24 * i + 16) = 0;
        }
      }
      if ( *(_QWORD *)a1 )
      {
        operator delete(*(void **)a1);
        *(_QWORD *)a1 = 0;
      }
      *((_DWORD *)a1 + 2) = 0;
    }
  }
  else
  {
    v2 = -2147024809;
    SdpDebugTrace(1u, L"SdpFreeParamSet", 0x21Du, -2147024809);
  }
  return v2;
}

```

## disassembly

```asm
0x1800025c8  push    rbx
0x1800025ca  push    rbp
0x1800025cb  push    rsi
0x1800025cc  push    rdi
0x1800025cd  sub     rsp, 28h
0x1800025d1  mov     rbx, rcx
0x1800025d4  test    rcx, rcx
0x1800025d7  jnz     short loc_1800025FB
0x1800025d9  mov     ebp, 80070057h
0x1800025de  lea     rdx, aSdpfreeparamse; "SdpFreeParamSet"
0x1800025e5  mov     r9d, ebp; int
0x1800025e8  lea     ecx, [rbx+1]; Level
0x1800025eb  mov     r8d, 21Dh; int
0x1800025f1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800025f6  jmp     loc_18000268E
0x1800025fb  xor     ebp, ebp
0x1800025fd  cmp     [rcx], rbp
0x180002600  jz      loc_18000268E
0x180002606  xor     esi, esi
0x180002608  cmp     [rcx+8], esi
0x18000260b  jbe     short loc_18000267B
0x18000260d  mov     rax, [rbx]
0x180002610  lea     rdi, [rsi+rsi*2]
0x180002614  mov     rcx, [rax+rdi*8]; bstrString
0x180002618  test    rcx, rcx
0x18000261b  jz      short loc_18000262A
0x18000261d  call    cs:__imp_SysFreeString
0x180002623  mov     rax, [rbx]
0x180002626  mov     [rax+rdi*8], rbp
0x18000262a  mov     rcx, [rbx]
0x18000262d  mov     rax, [rcx+rdi*8+10h]
0x180002632  cmp     [rcx+rdi*8+8], rax
0x180002637  jnz     short loc_18000263E
0x180002639  mov     [rcx+rdi*8+8], rbp
0x18000263e  mov     rax, [rbx]
0x180002641  mov     rcx, [rax+rdi*8+8]; bstrString
0x180002646  test    rcx, rcx
0x180002649  jz      short loc_180002659
0x18000264b  call    cs:__imp_SysFreeString
0x180002651  mov     rax, [rbx]
0x180002654  mov     [rax+rdi*8+8], rbp
0x180002659  mov     rax, [rbx]
0x18000265c  mov     rcx, [rax+rdi*8+10h]; bstrString
0x180002661  test    rcx, rcx
0x180002664  jz      short loc_180002674
0x180002666  call    cs:__imp_SysFreeString
0x18000266c  mov     rax, [rbx]
0x18000266f  mov     [rax+rdi*8+10h], rbp
0x180002674  inc     esi
0x180002676  cmp     esi, [rbx+8]
0x180002679  jb      short loc_18000260D
0x18000267b  mov     rcx, [rbx]; Block
0x18000267e  test    rcx, rcx
0x180002681  jz      short loc_18000268B
0x180002683  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002688  mov     [rbx], rbp
0x18000268b  mov     [rbx+8], ebp
0x18000268e  mov     eax, ebp
0x180002690  add     rsp, 28h
0x180002694  pop     rdi
0x180002695  pop     rsi
0x180002696  pop     rbp
0x180002697  pop     rbx
0x180002698  retn
```
