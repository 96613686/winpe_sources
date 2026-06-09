# WerUICreate

- ea: `0x1800038e0`
- end: `0x1800039d6`
- name: `WerUICreate`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002fec`
- `0x180003604`
- `0x1800038e0`
- `0x180005c9c`
- `0x180006990`

## import_xrefs

- `wer!WerpGetReportFlags` at `0x180003906`
- `wer!WerpGetReportFlags` at `0x180003906`

## pseudocode

```c
__int64 __fastcall WerUICreate(
        void *a1,
        int a2,
        int (*a3)(void *, struct _WER_UI_CALLBACK_INPUT *const),
        void *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        CEventUI **a8)
{
  int ReportFlags; // ebx
  CEventUI *v13; // rax
  CEventUI *v14; // rax
  CEventUI *v15; // rdi
  int v17[18]; // [rsp+40h] [rbp-48h] BYREF

  v17[0] = 0;
  ReportFlags = WerpGetReportFlags(a1, v17);
  if ( ReportFlags >= 0 )
  {
    v13 = (CEventUI *)operator new(0x3C8u);
    if ( v13 && (v14 = CEventUI::CEventUI(v13), (v15 = v14) != 0) )
    {
      ReportFlags = CEventUI::Initialize((__int64)v14, a1, a2, a3, a4, a5, a6, a7);
      if ( ReportFlags >= 0 )
      {
        ReportFlags = 0;
        *a8 = v15;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids,
          (unsigned int)ReportFlags);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)ReportFlags;
}

```

## disassembly

```asm
0x1800038e0  push    rbx
0x1800038e2  push    rbp
0x1800038e3  push    rsi
0x1800038e4  push    rdi
0x1800038e5  push    r14
0x1800038e7  push    r15
0x1800038e9  sub     rsp, 58h
0x1800038ed  mov     r15d, edx
0x1800038f0  mov     [rsp+88h+var_48], 0
0x1800038f8  lea     rdx, [rsp+88h+var_48]
0x1800038fd  mov     rbp, r9
0x180003900  mov     r14, r8
0x180003903  mov     rsi, rcx
0x180003906  call    cs:__imp_WerpGetReportFlags
0x18000390c  mov     ebx, eax
0x18000390e  test    eax, eax
0x180003910  js      loc_1800039C7
0x180003916  mov     ecx, 3C8h; Size
0x18000391b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003920  test    rax, rax
0x180003923  jz      loc_1800039C2
0x180003929  mov     rcx, rax; this
0x18000392c  call    ??0CEventUI@@QEAA@XZ; CEventUI::CEventUI(void)
0x180003931  mov     rdi, rax
0x180003934  test    rax, rax
0x180003937  jz      loc_1800039C2
0x18000393d  mov     rcx, [rsp+88h+arg_30]
0x180003945  mov     r9, r14
0x180003948  mov     [rsp+88h+var_50], rcx
0x18000394d  mov     r8d, r15d
0x180003950  mov     rcx, [rsp+88h+arg_28]
0x180003958  mov     rdx, rsi
0x18000395b  mov     [rsp+88h+var_58], rcx
0x180003960  mov     rcx, [rsp+88h+arg_20]
0x180003968  mov     [rsp+88h+var_60], rcx
0x18000396d  mov     rcx, rax
0x180003970  mov     [rsp+88h+var_68], rbp
0x180003975  call    ?Initialize@CEventUI@@QEAAJQEAXW4EVENTUI_STATE@@P6AHPEAXQEAU_WER_UI_CALLBACK_INPUT@@@Z2222@Z; CEventUI::Initialize(void * const,EVENTUI_STATE,int (*)(void *,_WER_UI_CALLBACK_INPUT * const),void *,void *,void *,void *)
0x18000397a  mov     ebx, eax
0x18000397c  test    eax, eax
0x18000397e  jns     short loc_1800039B3
0x180003980  mov     rcx, cs:WPP_GLOBAL_Control
0x180003987  lea     rax, WPP_GLOBAL_Control
0x18000398e  cmp     rcx, rax
0x180003991  jz      short loc_1800039C7
0x180003993  test    byte ptr [rcx+1Ch], 1
0x180003997  jz      short loc_1800039C7
0x180003999  mov     rcx, [rcx+10h]
0x18000399d  lea     r8, WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids
0x1800039a4  mov     edx, 0Ah
0x1800039a9  mov     r9d, ebx
0x1800039ac  call    WPP_SF_d
0x1800039b1  jmp     short loc_1800039C7
0x1800039b3  mov     rax, [rsp+88h+arg_38]
0x1800039bb  xor     ebx, ebx
0x1800039bd  mov     [rax], rdi
0x1800039c0  jmp     short loc_1800039C7
0x1800039c2  mov     ebx, 8007000Eh
0x1800039c7  mov     eax, ebx
0x1800039c9  add     rsp, 58h
0x1800039cd  pop     r15
0x1800039cf  pop     r14
0x1800039d1  pop     rdi
0x1800039d2  pop     rsi
0x1800039d3  pop     rbp
0x1800039d4  pop     rbx
0x1800039d5  retn
```
