# CInitialConsentUI::SetOptedinEndTaskOptions(_TASKDIALOG_BUTTON *,ulong,ulong *,ulong *)

- ea: `0x18000d4c0`
- end: `0x18000d6b1`
- name: `?SetOptedinEndTaskOptions@CInitialConsentUI@@AEAAJPEAU_TASKDIALOG_BUTTON@@KPEAK1@Z`
- size: `497`
- prototype: `__int64 __fastcall(CInitialConsentUI *__hidden this, struct _TASKDIALOG_BUTTON *, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000cbc8`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180008f3c`
- `0x1800096a8`
- `0x18000d4c0`

## import_xrefs

- `wer!WerpGetUIParamByIndex` at `0x18000d5cb`
- `wer!WerpGetUIParamByIndex` at `0x18000d5cb`
- `wer!WerpGetReportFlags` at `0x18000d51b`
- `wer!WerpGetReportFlags` at `0x18000d51b`

## pseudocode

```c
__int64 __fastcall CInitialConsentUI::SetOptedinEndTaskOptions(
        CInitialConsentUI *this,
        struct _TASKDIALOG_BUTTON *a2,
        __int64 a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int *v8; // r14
  int ReportFlags; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // ebx
  char *v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // [rsp+58h] [rbp+10h] BYREF
  int v20; // [rsp+60h] [rbp+18h] BYREF

  v19 = 0;
  v20 = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      v8 = a5;
      if ( a5 )
      {
        ReportFlags = WerpGetReportFlags(*((_QWORD *)this + 5), &v20);
        v10 = ReportFlags;
        if ( ReportFlags < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v10;
          v12 = 16;
          goto LABEL_8;
        }
        v14 = 0;
        if ( (v20 & 2) != 0 )
        {
          a2->nButtonID = 4;
          ReportFlags = UtilLoadString((char *)this + 88, 236);
          v10 = ReportFlags;
          if ( ReportFlags < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return v10;
            v12 = 17;
LABEL_8:
            v13 = (unsigned int)ReportFlags;
LABEL_9:
            WPP_SF_d(v11[2], v12, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids, v13);
            return v10;
          }
          v14 = 1;
          a2->pszButtonText = (PCWSTR)*((_QWORD *)this + 11);
        }
        if ( (int)WerpGetUIParamByIndex(*((_QWORD *)this + 5), 7, &v19) >= 0 )
        {
          v15 = (char *)this + 32 * v14;
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                   v15 + 88,
                                   v19) )
          {
            v10 = -2147024882;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return v10;
            v12 = 18;
            v13 = 2147942414LL;
            goto LABEL_9;
          }
          v16 = v14++;
          a2[v16].nButtonID = 2 * (v20 & 1) + 7;
          a2[v16].pszButtonText = (PCWSTR)*((_QWORD *)v15 + 11);
        }
        v17 = v14;
        a2[v17].nButtonID = 8;
        a2[v17].pszButtonText = (PCWSTR)3017;
        *v8 = 8;
        *a4 = v14 + 1;
        return 0;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000d4c0  mov     rax, rsp
0x18000d4c3  mov     [rax+8], rbx
0x18000d4c7  mov     [rax+20h], rbp
0x18000d4cb  mov     [rax+18h], r8d
0x18000d4cf  push    rsi
0x18000d4d0  push    rdi
0x18000d4d1  push    r12
0x18000d4d3  push    r14
0x18000d4d5  push    r15
0x18000d4d7  sub     rsp, 20h
0x18000d4db  mov     qword ptr [rax+10h], 0
0x18000d4e3  mov     r15, r9
0x18000d4e6  mov     dword ptr [rax+18h], 0
0x18000d4ed  mov     rdi, rdx
0x18000d4f0  mov     rsi, rcx
0x18000d4f3  test    rdx, rdx
0x18000d4f6  jz      loc_18000D667
0x18000d4fc  test    r9, r9
0x18000d4ff  jz      loc_18000D667
0x18000d505  mov     r14, [rsp+48h+arg_20]
0x18000d50a  test    r14, r14
0x18000d50d  jz      loc_18000D667
0x18000d513  mov     rcx, [rcx+28h]
0x18000d517  lea     rdx, [rax+18h]
0x18000d51b  call    cs:__imp_WerpGetReportFlags
0x18000d521  mov     ebx, eax
0x18000d523  test    eax, eax
0x18000d525  jns     short loc_18000D565
0x18000d527  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d52e  lea     rdx, WPP_GLOBAL_Control
0x18000d535  cmp     rcx, rdx
0x18000d538  jz      loc_18000D663
0x18000d53e  test    byte ptr [rcx+1Ch], 1
0x18000d542  jz      loc_18000D663
0x18000d548  mov     edx, 10h
0x18000d54d  mov     r9d, eax
0x18000d550  mov     rcx, [rcx+10h]
0x18000d554  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000d55b  call    WPP_SF_d
0x18000d560  jmp     loc_18000D663
0x18000d565  xor     ebx, ebx
0x18000d567  test    byte ptr [rsp+48h+arg_10], 2
0x18000d56c  jz      short loc_18000D5BD
0x18000d56e  mov     edx, 0ECh
0x18000d573  mov     dword ptr [rdi], 4
0x18000d579  lea     rcx, [rsi+58h]
0x18000d57d  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000d582  mov     ebx, eax
0x18000d584  test    eax, eax
0x18000d586  jns     short loc_18000D5B0
0x18000d588  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d58f  lea     rdx, WPP_GLOBAL_Control
0x18000d596  cmp     rcx, rdx
0x18000d599  jz      loc_18000D663
0x18000d59f  test    byte ptr [rcx+1Ch], 1
0x18000d5a3  jz      loc_18000D663
0x18000d5a9  mov     edx, 11h
0x18000d5ae  jmp     short loc_18000D54D
0x18000d5b0  mov     rax, [rsi+58h]
0x18000d5b4  mov     ebx, 1
0x18000d5b9  mov     [rdi+4], rax
0x18000d5bd  mov     rcx, [rsi+28h]
0x18000d5c1  lea     r8, [rsp+48h+arg_8]
0x18000d5c6  mov     edx, 7
0x18000d5cb  call    cs:__imp_WerpGetUIParamByIndex
0x18000d5d1  test    eax, eax
0x18000d5d3  js      short loc_18000D641
0x18000d5d5  mov     rdx, [rsp+48h+arg_8]
0x18000d5da  mov     eax, ebx
0x18000d5dc  shl     rax, 5
0x18000d5e0  add     rsi, rax
0x18000d5e3  mov     r12d, ebx
0x18000d5e6  lea     rcx, [rsi+58h]
0x18000d5ea  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000d5ef  test    al, al
0x18000d5f1  jnz     short loc_18000D621
0x18000d5f3  mov     ebx, 8007000Eh
0x18000d5f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5ff  lea     rdx, WPP_GLOBAL_Control
0x18000d606  cmp     rcx, rdx
0x18000d609  jz      short loc_18000D663
0x18000d60b  test    byte ptr [rcx+1Ch], 1
0x18000d60f  jz      short loc_18000D663
0x18000d611  mov     edx, 12h
0x18000d616  mov     r9d, 8007000Eh
0x18000d61c  jmp     loc_18000D550
0x18000d621  mov     eax, [rsp+48h+arg_10]
0x18000d625  lea     rcx, [r12+r12*2]
0x18000d629  and     eax, 1
0x18000d62c  inc     ebx
0x18000d62e  lea     eax, ds:7[rax*2]
0x18000d635  mov     [rdi+rcx*4], eax
0x18000d638  mov     rax, [rsi+58h]
0x18000d63c  mov     [rdi+rcx*4+4], rax
0x18000d641  mov     eax, ebx
0x18000d643  lea     rcx, [rax+rax*2]
0x18000d647  mov     eax, 8
0x18000d64c  mov     [rdi+rcx*4], eax
0x18000d64f  mov     qword ptr [rdi+rcx*4+4], 0BC9h
0x18000d658  mov     [r14], eax
0x18000d65b  lea     eax, [rbx+1]
0x18000d65e  mov     [r15], eax
0x18000d661  xor     ebx, ebx
0x18000d663  mov     eax, ebx
0x18000d665  jmp     short loc_18000D69A
0x18000d667  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d66e  lea     rdx, WPP_GLOBAL_Control
0x18000d675  cmp     rcx, rdx
0x18000d678  jz      short loc_18000D695
0x18000d67a  test    byte ptr [rcx+1Ch], 1
0x18000d67e  jz      short loc_18000D695
0x18000d680  mov     rcx, [rcx+10h]
0x18000d684  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000d68b  mov     edx, 0Fh
0x18000d690  call    WPP_SF_
0x18000d695  mov     eax, 80070057h
0x18000d69a  mov     rbx, [rsp+48h+arg_0]
0x18000d69f  mov     rbp, [rsp+48h+arg_18]
0x18000d6a4  add     rsp, 20h
0x18000d6a8  pop     r15
0x18000d6aa  pop     r14
0x18000d6ac  pop     r12
0x18000d6ae  pop     rdi
0x18000d6af  pop     rsi
0x18000d6b0  retn
```
