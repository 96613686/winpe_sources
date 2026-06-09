# CTask::HrGetRecycledPage(_GUID *,_XWIZARD_PAGE_DATA * *,int)

- ea: `0x18002336c`
- end: `0x180023490`
- name: `?HrGetRecycledPage@CTask@@AEAAJPEAU_GUID@@PEAPEAU_XWIZARD_PAGE_DATA@@H@Z`
- size: `292`
- prototype: `__int64 __fastcall(CTask *__hidden this, struct _GUID *, struct _XWIZARD_PAGE_DATA **, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021634`
- `0x180021d04`

## callees

- `0x180002562`
- `0x18000ae04`
- `0x18002336c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023411`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023411`

## pseudocode

```c
__int64 __fastcall CTask::HrGetRecycledPage(CTask *this, struct _GUID *a2, struct _XWIZARD_PAGE_DATA **a3, int a4)
{
  __int64 *v4; // rax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  char *v11; // rcx
  char *v12; // r8
  void *v13; // rcx
  PVOID *v14; // rcx

  v4 = (__int64 *)*((_QWORD *)this + 46);
  v8 = 1;
  do
  {
    if ( v4 == *((__int64 **)this + 45) )
      goto LABEL_14;
    v9 = *--v4;
    v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)(*v4 + 4);
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)(*v4 + 4) )
      v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)(v9 + 12);
  }
  while ( v10 );
  *a3 = (struct _XWIZARD_PAGE_DATA *)v9;
  if ( a4 )
  {
LABEL_13:
    v8 = 0;
LABEL_14:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_15;
  }
  v11 = (char *)*((_QWORD *)this + 45);
  v12 = (char *)*((_QWORD *)this + 46);
  while ( v11 != v12 )
  {
    if ( *v4 == *(_QWORD *)v11 )
    {
      memmove_0(v11, v11 + 8, (v12 - (v11 + 8)) & 0xFFFFFFFFFFFFFFF8uLL);
      *((_QWORD *)this + 46) -= 8LL;
      v13 = (void *)*((_QWORD *)*a3 + 20);
      if ( v13 )
      {
        CoTaskMemFree(v13);
        *((_QWORD *)*a3 + 20) = 0;
      }
      goto LABEL_13;
    }
    v11 += 8;
  }
  v8 = -2147418113;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, 2147549183LL);
    goto LABEL_14;
  }
LABEL_15:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x10) != 0 )
    WPP_SF_d(v14[2], 48, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18002336c  push    rbx
0x18002336e  push    rbp
0x18002336f  push    rsi
0x180023370  push    rdi
0x180023371  sub     rsp, 28h
0x180023375  mov     rax, [rcx+170h]
0x18002337c  mov     rsi, r8
0x18002337f  mov     r8, rdx
0x180023382  mov     rdi, rcx
0x180023385  mov     ebx, 1
0x18002338a  lea     rbp, WPP_GLOBAL_Control
0x180023391  cmp     rax, [rdi+168h]
0x180023398  jz      loc_180023427
0x18002339e  mov     rcx, [r8]
0x1800233a1  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800233a5  mov     rdx, [rax]
0x1800233a8  sub     rcx, [rdx+4]
0x1800233ac  jnz     short loc_1800233B6
0x1800233ae  mov     rcx, [r8+8]
0x1800233b2  sub     rcx, [rdx+0Ch]
0x1800233b6  test    rcx, rcx
0x1800233b9  jnz     short loc_18002338A
0x1800233bb  mov     [rsi], rdx
0x1800233be  test    r9d, r9d
0x1800233c1  jnz     short loc_180023425
0x1800233c3  mov     rcx, [rdi+168h]; void *
0x1800233ca  mov     r8, [rdi+170h]
0x1800233d1  cmp     rcx, r8
0x1800233d4  jz      loc_18002345C
0x1800233da  mov     rdx, [rcx]
0x1800233dd  lea     r9, [rcx+8]
0x1800233e1  cmp     [rax], rdx
0x1800233e4  jz      short loc_1800233EB
0x1800233e6  mov     rcx, r9
0x1800233e9  jmp     short loc_1800233D1
0x1800233eb  sub     r8, r9
0x1800233ee  mov     rdx, r9; Src
0x1800233f1  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x1800233f5  call    memmove_0
0x1800233fa  add     qword ptr [rdi+170h], 0FFFFFFFFFFFFFFF8h
0x180023402  mov     rax, [rsi]
0x180023405  mov     rcx, [rax+0A0h]; pv
0x18002340c  test    rcx, rcx
0x18002340f  jz      short loc_180023425
0x180023411  call    cs:__imp_CoTaskMemFree
0x180023417  mov     rax, [rsi]
0x18002341a  mov     qword ptr [rax+0A0h], 0
0x180023425  xor     ebx, ebx
0x180023427  mov     rcx, cs:WPP_GLOBAL_Control
0x18002342e  cmp     rcx, rbp
0x180023431  jz      short loc_180023451
0x180023433  test    byte ptr [rcx+1Ch], 10h
0x180023437  jz      short loc_180023451
0x180023439  mov     rcx, [rcx+10h]
0x18002343d  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180023444  mov     edx, 30h ; '0'
0x180023449  mov     r9d, ebx
0x18002344c  call    WPP_SF_d
0x180023451  mov     eax, ebx
0x180023453  add     rsp, 28h
0x180023457  pop     rdi
0x180023458  pop     rsi
0x180023459  pop     rbp
0x18002345a  pop     rbx
0x18002345b  retn
0x18002345c  mov     ebx, 8000FFFFh
0x180023461  mov     rcx, cs:WPP_GLOBAL_Control
0x180023468  cmp     rcx, rbp
0x18002346b  jz      short loc_180023451
0x18002346d  test    byte ptr [rcx+1Ch], 4
0x180023471  jz      short loc_18002342E
0x180023473  mov     rcx, [rcx+10h]
0x180023477  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x18002347e  mov     edx, 2Fh ; '/'
0x180023483  mov     r9d, 8000FFFFh
0x180023489  call    WPP_SF_d
0x18002348e  jmp     short loc_180023427
```
