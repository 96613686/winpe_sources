# CPEnumXWizardControlPage::Skip(ulong)

- ea: `0x180029750`
- end: `0x18002987c`
- name: `?Skip@CPEnumXWizardControlPage@@UEAAJK@Z`
- size: `300`
- prototype: `__int64 __fastcall(CPEnumXWizardControlPage *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x180029750`
- `0x180029884`
- `0x1800298e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800297e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800297e3`

## pseudocode

```c
__int64 __fastcall CPEnumXWizardControlPage::Skip(CPEnumXWizardControlPage *this, __int64 a2, __int64 a3)
{
  unsigned int v3; // esi
  int v4; // edi
  unsigned int v6; // ecx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdx
  PVOID *v10; // rcx

  v3 = 0;
  v4 = a2;
  if ( (int)a2 >= 0 )
  {
    v6 = a2 + *((_DWORD *)this + 26);
    if ( v6 >= (unsigned __int64)((__int64)(*((_QWORD *)this + 11) - *((_QWORD *)this + 10)) >> 3) )
      v3 = 1;
    else
      *((_DWORD *)this + 26) = v6;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_dddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (__int64)(*((_QWORD *)this + 11) - *((_QWORD *)this + 10)) >> 3,
      *((_DWORD *)this + 26),
      *((_DWORD *)this + 27),
      -(int)a2);
  do
  {
    v7 = *((_QWORD *)this + 11);
    if ( v7 == *((_QWORD *)this + 10) )
      break;
    CoTaskMemFree(*(LPVOID *)(v7 - 8));
    v7 = *((_QWORD *)this + 11);
    if ( *((_QWORD *)this + 10) != v7 )
    {
      v7 -= 8;
      *((_QWORD *)this + 11) = v7;
    }
    ++v4;
  }
  while ( v4 < 0 );
  v8 = *((_QWORD *)this + 10);
  *((_DWORD *)this + 27) = -1;
  v9 = (v7 - v8) >> 3;
  *((_DWORD *)this + 26) = v9;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_16:
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
        WPP_SF_d(v10[2], 14, &WPP_d4256cb9cd783c1ed4ccbaed64b6cca7_Traceguids, v3);
      return v3;
    }
    WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, a3, (*((_QWORD *)this + 11) - v8) >> 3, v9, -1);
LABEL_15:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  return v3;
}

```

## disassembly

```asm
0x180029750  push    rbx
0x180029752  push    rbp
0x180029753  push    rsi
0x180029754  push    rdi
0x180029755  sub     rsp, 48h
0x180029759  xor     esi, esi
0x18002975b  lea     rbp, WPP_GLOBAL_Control
0x180029762  mov     edi, edx
0x180029764  mov     rbx, rcx
0x180029767  test    edx, edx
0x180029769  js      short loc_180029795
0x18002976b  mov     ecx, [rcx+68h]
0x18002976e  add     ecx, edx
0x180029770  mov     rdx, [rbx+58h]
0x180029774  sub     rdx, [rbx+50h]
0x180029778  sar     rdx, 3
0x18002977c  mov     eax, ecx
0x18002977e  cmp     rax, rdx
0x180029781  jnb     short loc_18002978B
0x180029783  mov     [rbx+68h], ecx
0x180029786  jmp     loc_180029847
0x18002978b  mov     esi, 1
0x180029790  jmp     loc_180029847
0x180029795  mov     rcx, cs:WPP_GLOBAL_Control
0x18002979c  cmp     rcx, rbp
0x18002979f  jz      short loc_1800297D5
0x1800297a1  test    byte ptr [rcx+1Ch], 8
0x1800297a5  jz      short loc_1800297D5
0x1800297a7  mov     r9, [rbx+58h]
0x1800297ab  mov     eax, edx
0x1800297ad  mov     rcx, [rcx+10h]
0x1800297b1  neg     eax
0x1800297b3  cmovs   eax, edx
0x1800297b6  sub     r9, [rbx+50h]
0x1800297ba  mov     [rsp+68h+var_38], eax
0x1800297be  mov     eax, [rbx+6Ch]
0x1800297c1  mov     [rsp+68h+var_40], eax
0x1800297c5  mov     eax, [rbx+68h]
0x1800297c8  sar     r9, 3
0x1800297cc  mov     [rsp+68h+var_48], eax
0x1800297d0  call    WPP_SF_dddd
0x1800297d5  mov     rdx, [rbx+58h]
0x1800297d9  cmp     rdx, [rbx+50h]
0x1800297dd  jz      short loc_180029800
0x1800297df  mov     rcx, [rdx-8]; pv
0x1800297e3  call    cs:__imp_CoTaskMemFree
0x1800297e9  mov     rdx, [rbx+58h]
0x1800297ed  cmp     [rbx+50h], rdx
0x1800297f1  jz      short loc_1800297FB
0x1800297f3  add     rdx, 0FFFFFFFFFFFFFFF8h
0x1800297f7  mov     [rbx+58h], rdx
0x1800297fb  add     edi, 1
0x1800297fe  js      short loc_1800297D5
0x180029800  mov     rax, [rbx+50h]
0x180029804  sub     rdx, rax
0x180029807  mov     dword ptr [rbx+6Ch], 0FFFFFFFFh
0x18002980e  sar     rdx, 3
0x180029812  mov     [rbx+68h], edx
0x180029815  mov     rcx, cs:WPP_GLOBAL_Control
0x18002981c  cmp     rcx, rbp
0x18002981f  jz      short loc_180029871
0x180029821  test    byte ptr [rcx+1Ch], 8
0x180029825  jz      short loc_18002984E
0x180029827  mov     r9, [rbx+58h]
0x18002982b  mov     rcx, [rcx+10h]
0x18002982f  sub     r9, rax
0x180029832  sar     r9, 3
0x180029836  mov     [rsp+68h+var_40], 0FFFFFFFFh
0x18002983e  mov     [rsp+68h+var_48], edx
0x180029842  call    WPP_SF_ddd
0x180029847  mov     rcx, cs:WPP_GLOBAL_Control
0x18002984e  cmp     rcx, rbp
0x180029851  jz      short loc_180029871
0x180029853  test    byte ptr [rcx+1Ch], 10h
0x180029857  jz      short loc_180029871
0x180029859  mov     rcx, [rcx+10h]
0x18002985d  lea     r8, WPP_d4256cb9cd783c1ed4ccbaed64b6cca7_Traceguids
0x180029864  mov     edx, 0Eh
0x180029869  mov     r9d, esi
0x18002986c  call    WPP_SF_d
0x180029871  mov     eax, esi
0x180029873  add     rsp, 48h
0x180029877  pop     rdi
0x180029878  pop     rsi
0x180029879  pop     rbp
0x18002987a  pop     rbx
0x18002987b  retn
```
