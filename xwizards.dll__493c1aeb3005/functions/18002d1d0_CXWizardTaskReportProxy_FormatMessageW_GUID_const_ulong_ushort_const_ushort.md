# CXWizardTaskReportProxy::FormatMessageW(_GUID const *,ulong,ushort * const,ushort * *)

- ea: `0x18002d1d0`
- end: `0x18002d317`
- name: `?FormatMessageW@CXWizardTaskReportProxy@@UEAAJPEBU_GUID@@KQEAGPEAPEAG@Z`
- size: `327`
- prototype: `__int64 __fastcall(CXWizardTaskReportProxy *__hidden this, const struct _GUID *, unsigned int, unsigned __int16 *const, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180008634`
- `0x18000ae04`
- `0x18001a950`
- `0x18001abe4`
- `0x18001af64`
- `0x18001b6e4`
- `0x18002d1d0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d298`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d298`

## pseudocode

```c
__int64 __fastcall CXWizardTaskReportProxy::FormatMessageW(
        CXWizardTaskReportProxy *this,
        const struct _GUID *a2,
        unsigned int a3,
        unsigned __int16 *const a4,
        unsigned __int16 **a5)
{
  int MarshalID; // ebx
  __int64 v10; // rcx
  unsigned __int16 v11; // si
  int v12; // eax
  unsigned __int16 *v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // r14d
  unsigned __int16 *v17; // rax
  unsigned __int16 v19[2]; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-40h] BYREF

  v19[0] = 0;
  MarshalID = HrCreateMarshalID(v19, 0, 0);
  if ( MarshalID >= 0 )
  {
    v10 = *((_QWORD *)this + 8);
    v11 = v19[0];
    if ( !a4 )
      a4 = (unsigned __int16 *const)&dword_18003C1AC;
    if ( !a2 )
      a2 = &GUID_NULL;
    MarshalID = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD, unsigned __int16 *const, unsigned __int16))(*(_QWORD *)v10 + 48LL))(
                  v10,
                  a2,
                  a3,
                  a4,
                  v19[0]);
    if ( MarshalID >= 0 )
    {
      v20 = 0;
      *(_DWORD *)v19 = 0;
      v12 = HrMapMarshalID(v11, (void **)&v20, (unsigned int *)v19);
      v13 = v20;
      MarshalID = v12;
      if ( v20 )
      {
        if ( *(_DWORD *)v19 )
        {
          v14 = -1;
          do
            ++v14;
          while ( v20[v14] );
          v15 = (unsigned int)(v14 + 1);
          v16 = v15;
          v17 = (unsigned __int16 *)LocalAlloc(0, 2 * v15);
          *a5 = v17;
          if ( v17 )
          {
            *v17 = 0;
            StringCchCopyW(*a5, v16, (size_t *)v13);
          }
          else
          {
            MarshalID = -2147024882;
          }
          HrUnmapMarshalID(v13);
        }
      }
    }
    HrDestroyMarshalID(v11);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_95a2430a111d3b5e594174780a910ded_Traceguids,
      (unsigned int)MarshalID);
  return (unsigned int)MarshalID;
}

```

## disassembly

```asm
0x18002d1d0  push    rbx
0x18002d1d2  push    rbp
0x18002d1d3  push    rsi
0x18002d1d4  push    rdi
0x18002d1d5  push    r14
0x18002d1d7  push    r15
0x18002d1d9  sub     rsp, 48h
0x18002d1dd  mov     r14d, r8d
0x18002d1e0  mov     rbp, rdx
0x18002d1e3  mov     rsi, rcx
0x18002d1e6  xor     r15d, r15d
0x18002d1e9  xor     r8d, r8d; unsigned int
0x18002d1ec  mov     [rsp+78h+var_48], r15w
0x18002d1f2  xor     edx, edx; unsigned int
0x18002d1f4  lea     rcx, [rsp+78h+var_48]; unsigned __int16 *
0x18002d1f9  mov     rdi, r9
0x18002d1fc  call    ?HrCreateMarshalID@@YAJPEAGKK@Z; HrCreateMarshalID(ushort *,ulong,ulong)
0x18002d201  mov     ebx, eax
0x18002d203  test    eax, eax
0x18002d205  js      loc_18002D2D7
0x18002d20b  mov     rcx, [rsi+40h]
0x18002d20f  lea     rdx, dword_18003C1AC
0x18002d216  movzx   esi, [rsp+78h+var_48]
0x18002d21b  test    rdi, rdi
0x18002d21e  mov     r8d, r14d
0x18002d221  mov     [rsp+78h+var_58], si
0x18002d226  cmovz   rdi, rdx
0x18002d22a  lea     rdx, GUID_NULL
0x18002d231  mov     rax, [rcx]
0x18002d234  test    rbp, rbp
0x18002d237  mov     r9, rdi
0x18002d23a  cmovz   rbp, rdx
0x18002d23e  mov     rdx, rbp
0x18002d241  mov     rax, [rax+30h]
0x18002d245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d24a  mov     ebx, eax
0x18002d24c  test    eax, eax
0x18002d24e  js      short loc_18002D2CF
0x18002d250  lea     r8, [rsp+78h+var_48]; unsigned int *
0x18002d255  mov     [rsp+78h+var_40], r15
0x18002d25a  lea     rdx, [rsp+78h+var_40]; void **
0x18002d25f  mov     dword ptr [rsp+78h+var_48], r15d
0x18002d264  movzx   ecx, si; unsigned __int16
0x18002d267  call    ?HrMapMarshalID@@YAJGPEAPEAXPEAK@Z; HrMapMarshalID(ushort,void * *,ulong *)
0x18002d26c  mov     rdi, [rsp+78h+var_40]
0x18002d271  mov     ebx, eax
0x18002d273  test    rdi, rdi
0x18002d276  jz      short loc_18002D2CF
0x18002d278  cmp     dword ptr [rsp+78h+var_48], r15d
0x18002d27d  jz      short loc_18002D2CF
0x18002d27f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d283  inc     rax
0x18002d286  cmp     [rdi+rax*2], r15w
0x18002d28b  jnz     short loc_18002D283
0x18002d28d  inc     eax
0x18002d28f  xor     ecx, ecx; uFlags
0x18002d291  mov     r14d, eax
0x18002d294  lea     rdx, [rax+rax]; uBytes
0x18002d298  call    cs:__imp_LocalAlloc
0x18002d29e  mov     rcx, [rsp+78h+arg_20]
0x18002d2a6  mov     [rcx], rax
0x18002d2a9  test    rax, rax
0x18002d2ac  jz      short loc_18002D2C2
0x18002d2ae  mov     [rax], r15w
0x18002d2b2  mov     r8, rdi; unsigned __int16 *
0x18002d2b5  mov     rcx, [rcx]; unsigned __int16 *
0x18002d2b8  mov     edx, r14d; unsigned __int64
0x18002d2bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d2c0  jmp     short loc_18002D2C7
0x18002d2c2  mov     ebx, 8007000Eh
0x18002d2c7  mov     rcx, rdi; void *
0x18002d2ca  call    ?HrUnmapMarshalID@@YAJPEAX@Z; HrUnmapMarshalID(void *)
0x18002d2cf  movzx   ecx, si; unsigned __int16
0x18002d2d2  call    ?HrDestroyMarshalID@@YAJG@Z; HrDestroyMarshalID(ushort)
0x18002d2d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2de  lea     rax, WPP_GLOBAL_Control
0x18002d2e5  cmp     rcx, rax
0x18002d2e8  jz      short loc_18002D308
0x18002d2ea  test    byte ptr [rcx+1Ch], 10h
0x18002d2ee  jz      short loc_18002D308
0x18002d2f0  mov     rcx, [rcx+10h]
0x18002d2f4  lea     r8, WPP_95a2430a111d3b5e594174780a910ded_Traceguids
0x18002d2fb  mov     edx, 0Ah
0x18002d300  mov     r9d, ebx
0x18002d303  call    WPP_SF_d
0x18002d308  mov     eax, ebx
0x18002d30a  add     rsp, 48h
0x18002d30e  pop     r15
0x18002d310  pop     r14
0x18002d312  pop     rdi
0x18002d313  pop     rsi
0x18002d314  pop     rbp
0x18002d315  pop     rbx
0x18002d316  retn
```
