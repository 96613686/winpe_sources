# CInitialConsentUI::SetOptionButtons(_TASKDIALOG_BUTTON *,ulong,ulong *,ulong *)

- ea: `0x18000d6b8`
- end: `0x18000da99`
- name: `?SetOptionButtons@CInitialConsentUI@@AEAAJPEAU_TASKDIALOG_BUTTON@@KPEAK1@Z`
- size: `993`
- prototype: `__int64 __fastcall(CInitialConsentUI *this, struct _TASKDIALOG_BUTTON *, __int64, unsigned int *, unsigned int *)`
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
- `0x18000d6b8`

## import_xrefs

- `wer!WerpGetUIParamByIndex` at `0x18000d7d3`
- `wer!WerpGetUIParamByIndex` at `0x18000d953`
- `wer!WerpGetUIParamByIndex` at `0x18000d7d3`
- `wer!WerpGetUIParamByIndex` at `0x18000d953`
- `wer!WerpIsTransportAvailable` at `0x18000d7ac`
- `wer!WerpIsTransportAvailable` at `0x18000d7ac`
- `wer!WerpIsDisabled` at `0x18000d720`
- `wer!WerpIsDisabled` at `0x18000d720`
- `wer!WerpGetReportFlags` at `0x18000d771`
- `wer!WerpGetReportFlags` at `0x18000d771`

## pseudocode

```c
__int64 __fastcall CInitialConsentUI::SetOptionButtons(
        CInitialConsentUI *this,
        struct _TASKDIALOG_BUTTON *a2,
        __int64 a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int *v7; // r12
  int IsDisabled; // eax
  unsigned int UIParamByIndex; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // edi
  int IsTransportAvailable; // eax
  int v15; // ecx
  __int64 v16; // r8
  struct _TASKDIALOG_BUTTON *v17; // r15
  int v18; // eax
  __int64 v19; // rdx
  char *v20; // r13
  int v21; // ecx
  __int64 v22; // r15
  __int64 v23; // rcx
  __int64 v24; // r15
  char *v25; // r13
  __int64 v26; // rax
  __int64 v27; // rcx
  _QWORD v29[2]; // [rsp+20h] [rbp-10h] BYREF
  int v30; // [rsp+78h] [rbp+48h] BYREF
  int v31; // [rsp+80h] [rbp+50h] BYREF
  unsigned int *v32; // [rsp+88h] [rbp+58h]

  v32 = a4;
  v29[0] = 0;
  v30 = 0;
  v31 = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      v7 = a5;
      if ( a5 )
      {
        *a5 = 2;
        IsDisabled = WerpIsDisabled(*((_QWORD *)this + 5), &v30);
        UIParamByIndex = IsDisabled;
        if ( IsDisabled < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return UIParamByIndex;
          v11 = 20;
          goto LABEL_8;
        }
        IsDisabled = WerpGetReportFlags(*((_QWORD *)this + 5), &v31);
        UIParamByIndex = IsDisabled;
        if ( IsDisabled < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return UIParamByIndex;
          v11 = 21;
          goto LABEL_8;
        }
        v13 = 0;
        IsTransportAvailable = WerpIsTransportAvailable(0, 0);
        if ( !v30 )
        {
          a2->nButtonID = 4;
          UIParamByIndex = WerpGetUIParamByIndex(
                             *((_QWORD *)this + 5),
                             (unsigned int)(IsTransportAvailable != 0) + 5,
                             v29);
          if ( (UIParamByIndex & 0x80000000) != 0 || !v29[0] )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids);
            return UIParamByIndex;
          }
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                   (char *)this + 88,
                                   v29[0]) )
          {
            UIParamByIndex = -2147024882;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return UIParamByIndex;
            v11 = 23;
            goto LABEL_21;
          }
          v13 = 1;
          a2->pszButtonText = (PCWSTR)*((_QWORD *)this + 11);
        }
        v15 = v31 & 3;
        if ( (v31 & 3) != 0 )
        {
          if ( *(_DWORD *)this != 3 )
            goto LABEL_36;
          if ( (v31 & 1) != 0 )
          {
            if ( (v31 & 2) == 0 )
            {
              v16 = v13;
              v17 = &a2[v13];
              v18 = 10;
              v17->nButtonID = 10;
              goto LABEL_28;
            }
LABEL_36:
            v16 = v13;
            v19 = 0;
            v17 = &a2[v13];
            v18 = 6;
            v17->nButtonID = 6;
            v21 = v15 - 1;
            if ( v21 )
            {
              if ( (unsigned int)(v21 - 1) <= 1 )
                v19 = 236;
              goto LABEL_29;
            }
LABEL_28:
            v19 = 240;
LABEL_29:
            *v7 = v18;
            v20 = (char *)this + 32 * v16;
            IsDisabled = UtilLoadString(v20 + 88, v19);
            UIParamByIndex = IsDisabled;
            if ( IsDisabled < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                return UIParamByIndex;
              v11 = 24;
              goto LABEL_8;
            }
            v17->pszButtonText = (PCWSTR)*((_QWORD *)v20 + 11);
            goto LABEL_46;
          }
        }
        if ( (int)WerpGetUIParamByIndex(*((_QWORD *)this + 5), 7, v29) < 0 )
          goto LABEL_47;
        v22 = 32LL * v13;
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 (char *)this + v22 + 88,
                                 v29[0]) )
        {
          UIParamByIndex = -2147024882;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return UIParamByIndex;
          v11 = 25;
LABEL_21:
          v12 = 2147942414LL;
          goto LABEL_9;
        }
        v23 = v13;
        a2[v23].nButtonID = 2;
        a2[v23].pszButtonText = *(PCWSTR *)((char *)this + v22 + 88);
LABEL_46:
        ++v13;
LABEL_47:
        if ( (v31 & 8) != 0 )
        {
          v24 = v13;
          a2[v13].nButtonID = 5;
          v25 = (char *)this + 32 * v13;
          IsDisabled = UtilLoadString(v25 + 88, 237);
          UIParamByIndex = IsDisabled;
          if ( IsDisabled < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return UIParamByIndex;
            v11 = 26;
LABEL_8:
            v12 = (unsigned int)IsDisabled;
LABEL_9:
            WPP_SF_d(v10[2], v11, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids, v12);
            return UIParamByIndex;
          }
          ++v13;
          a2[v24].pszButtonText = (PCWSTR)*((_QWORD *)v25 + 11);
        }
        if ( *(_DWORD *)this == 3 )
        {
          v26 = v13++;
          v27 = v26;
          a2[v27].nButtonID = 8;
          a2[v27].pszButtonText = (PCWSTR)3017;
          *v7 = 8;
        }
        UIParamByIndex = 0;
        *v32 = v13;
        return UIParamByIndex;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000d6b8  mov     [rsp-38h+arg_0], rbx
0x18000d6bd  mov     [rsp-38h+arg_18], r9
0x18000d6c2  mov     [rsp-38h+arg_10], r8d
0x18000d6c7  push    rbp
0x18000d6c8  push    rsi
0x18000d6c9  push    rdi
0x18000d6ca  push    r12
0x18000d6cc  push    r13
0x18000d6ce  push    r14
0x18000d6d0  push    r15
0x18000d6d2  mov     rbp, rsp
0x18000d6d5  sub     rsp, 30h
0x18000d6d9  xor     r13d, r13d
0x18000d6dc  mov     rax, r9
0x18000d6df  mov     [rbp+var_10], r13
0x18000d6e3  mov     rsi, rdx
0x18000d6e6  mov     [rbp+arg_8], r13d
0x18000d6ea  mov     r14, rcx
0x18000d6ed  mov     [rbp+arg_10], r13d
0x18000d6f1  test    rdx, rdx
0x18000d6f4  jz      loc_18000DA51
0x18000d6fa  test    rax, rax
0x18000d6fd  jz      loc_18000DA51
0x18000d703  mov     r12, [rbp+arg_20]
0x18000d707  test    r12, r12
0x18000d70a  jz      loc_18000DA51
0x18000d710  mov     dword ptr [r12], 2
0x18000d718  lea     rdx, [rbp+arg_8]
0x18000d71c  mov     rcx, [rcx+28h]
0x18000d720  call    cs:__imp_WerpIsDisabled
0x18000d726  mov     ebx, eax
0x18000d728  test    eax, eax
0x18000d72a  jns     short loc_18000D769
0x18000d72c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d733  lea     rdx, WPP_GLOBAL_Control
0x18000d73a  cmp     rcx, rdx
0x18000d73d  jz      loc_18000DA4D
0x18000d743  test    byte ptr [rcx+1Ch], 1
0x18000d747  jz      loc_18000DA4D
0x18000d74d  lea     edx, [r13+14h]
0x18000d751  mov     r9d, eax
0x18000d754  mov     rcx, [rcx+10h]
0x18000d758  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000d75f  call    WPP_SF_d
0x18000d764  jmp     loc_18000DA4D
0x18000d769  mov     rcx, [r14+28h]
0x18000d76d  lea     rdx, [rbp+arg_10]
0x18000d771  call    cs:__imp_WerpGetReportFlags
0x18000d777  mov     ebx, eax
0x18000d779  test    eax, eax
0x18000d77b  jns     short loc_18000D7A5
0x18000d77d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d784  lea     rdx, WPP_GLOBAL_Control
0x18000d78b  cmp     rcx, rdx
0x18000d78e  jz      loc_18000DA4D
0x18000d794  test    byte ptr [rcx+1Ch], 1
0x18000d798  jz      loc_18000DA4D
0x18000d79e  mov     edx, 15h
0x18000d7a3  jmp     short loc_18000D751
0x18000d7a5  xor     edx, edx
0x18000d7a7  xor     ecx, ecx
0x18000d7a9  mov     edi, r13d
0x18000d7ac  call    cs:__imp_WerpIsTransportAvailable
0x18000d7b2  cmp     [rbp+arg_8], r13d
0x18000d7b6  jnz     loc_18000D840
0x18000d7bc  neg     eax
0x18000d7be  mov     dword ptr [rsi], 4
0x18000d7c4  mov     rcx, [r14+28h]
0x18000d7c8  lea     r8, [rbp+var_10]
0x18000d7cc  sbb     edx, edx
0x18000d7ce  neg     edx
0x18000d7d0  add     edx, 5
0x18000d7d3  call    cs:__imp_WerpGetUIParamByIndex
0x18000d7d9  mov     ebx, eax
0x18000d7db  test    eax, eax
0x18000d7dd  js      loc_18000D8CA
0x18000d7e3  mov     rdx, [rbp+var_10]
0x18000d7e7  test    rdx, rdx
0x18000d7ea  jz      loc_18000D8CA
0x18000d7f0  lea     rcx, [r14+58h]
0x18000d7f4  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000d7f9  test    al, al
0x18000d7fb  jnz     short loc_18000D833
0x18000d7fd  mov     ebx, 8007000Eh
0x18000d802  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d809  lea     rdx, WPP_GLOBAL_Control
0x18000d810  cmp     rcx, rdx
0x18000d813  jz      loc_18000DA4D
0x18000d819  test    byte ptr [rcx+1Ch], 1
0x18000d81d  jz      loc_18000DA4D
0x18000d823  mov     edx, 17h
0x18000d828  mov     r9d, 8007000Eh
0x18000d82e  jmp     loc_18000D754
0x18000d833  mov     rax, [r14+58h]
0x18000d837  mov     edi, 1
0x18000d83c  mov     [rsi+4], rax
0x18000d840  mov     eax, [rbp+arg_10]
0x18000d843  mov     ecx, eax
0x18000d845  and     ecx, 3
0x18000d848  jz      loc_18000D946
0x18000d84e  cmp     dword ptr [r14], 3
0x18000d852  jnz     loc_18000D905
0x18000d858  test    al, 1
0x18000d85a  jz      loc_18000D946
0x18000d860  test    al, 2
0x18000d862  jnz     loc_18000D905
0x18000d868  mov     r8d, edi
0x18000d86b  lea     rax, [r8+r8*2]
0x18000d86f  lea     r15, [rsi+rax*4]
0x18000d873  mov     eax, 0Ah
0x18000d878  mov     [r15], eax
0x18000d87b  mov     edx, 0F0h
0x18000d880  shl     r8, 5
0x18000d884  mov     [r12], eax
0x18000d888  lea     r13, [r8+r14]
0x18000d88c  lea     rcx, [r13+58h]
0x18000d890  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000d895  mov     ebx, eax
0x18000d897  test    eax, eax
0x18000d899  jns     loc_18000D93C
0x18000d89f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8a6  lea     rdx, WPP_GLOBAL_Control
0x18000d8ad  cmp     rcx, rdx
0x18000d8b0  jz      loc_18000DA4D
0x18000d8b6  test    byte ptr [rcx+1Ch], 1
0x18000d8ba  jz      loc_18000DA4D
0x18000d8c0  mov     edx, 18h
0x18000d8c5  jmp     loc_18000D751
0x18000d8ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8d1  lea     rdx, WPP_GLOBAL_Control
0x18000d8d8  cmp     rcx, rdx
0x18000d8db  jz      loc_18000DA4D
0x18000d8e1  test    byte ptr [rcx+1Ch], 1
0x18000d8e5  jz      loc_18000DA4D
0x18000d8eb  mov     rcx, [rcx+10h]
0x18000d8ef  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000d8f6  mov     edx, 16h
0x18000d8fb  call    WPP_SF_
0x18000d900  jmp     loc_18000DA4D
0x18000d905  mov     r8d, edi
0x18000d908  mov     edx, r13d
0x18000d90b  lea     rax, [r8+r8*2]
0x18000d90f  lea     r15, [rsi+rax*4]
0x18000d913  mov     eax, 6
0x18000d918  mov     [r15], eax
0x18000d91b  sub     ecx, 1
0x18000d91e  jz      loc_18000D87B
0x18000d924  sub     ecx, 1
0x18000d927  jz      short loc_18000D932
0x18000d929  cmp     ecx, 1
0x18000d92c  jnz     loc_18000D880
0x18000d932  mov     edx, 0ECh
0x18000d937  jmp     loc_18000D880
0x18000d93c  mov     rax, [r13+58h]
0x18000d940  mov     [r15+4], rax
0x18000d944  jmp     short loc_18000D9BF
0x18000d946  mov     rcx, [r14+28h]
0x18000d94a  lea     r8, [rbp+var_10]
0x18000d94e  mov     edx, 7
0x18000d953  call    cs:__imp_WerpGetUIParamByIndex
0x18000d959  test    eax, eax
0x18000d95b  js      short loc_18000D9C1
0x18000d95d  mov     rdx, [rbp+var_10]
0x18000d961  lea     rcx, [r14+58h]
0x18000d965  mov     r15d, edi
0x18000d968  shl     r15, 5
0x18000d96c  add     rcx, r15
0x18000d96f  mov     ebx, edi
0x18000d971  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000d976  test    al, al
0x18000d978  jnz     short loc_18000D9AA
0x18000d97a  mov     ebx, 8007000Eh
0x18000d97f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d986  lea     rdx, WPP_GLOBAL_Control
0x18000d98d  cmp     rcx, rdx
0x18000d990  jz      loc_18000DA4D
0x18000d996  test    byte ptr [rcx+1Ch], 1
0x18000d99a  jz      loc_18000DA4D
0x18000d9a0  mov     edx, 19h
0x18000d9a5  jmp     loc_18000D828
0x18000d9aa  lea     rcx, [rbx+rbx*2]
0x18000d9ae  mov     dword ptr [rsi+rcx*4], 2
0x18000d9b5  mov     rax, [r15+r14+58h]
0x18000d9ba  mov     [rsi+rcx*4+4], rax
0x18000d9bf  inc     edi
0x18000d9c1  test    byte ptr [rbp+arg_10], 8
0x18000d9c5  jz      short loc_18000DA1F
0x18000d9c7  mov     eax, edi
0x18000d9c9  mov     edx, 0EDh
0x18000d9ce  lea     r15, [rax+rax*2]
0x18000d9d2  shl     rax, 5
0x18000d9d6  mov     dword ptr [rsi+r15*4], 5
0x18000d9de  lea     r13, [rax+r14]
0x18000d9e2  lea     rcx, [r13+58h]
0x18000d9e6  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000d9eb  mov     ebx, eax
0x18000d9ed  test    eax, eax
0x18000d9ef  jns     short loc_18000DA14
0x18000d9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9f8  lea     rdx, WPP_GLOBAL_Control
0x18000d9ff  cmp     rcx, rdx
0x18000da02  jz      short loc_18000DA4D
0x18000da04  test    byte ptr [rcx+1Ch], 1
0x18000da08  jz      short loc_18000DA4D
0x18000da0a  mov     edx, 1Ah
0x18000da0f  jmp     loc_18000D751
0x18000da14  mov     rax, [r13+58h]
0x18000da18  inc     edi
0x18000da1a  mov     [rsi+r15*4+4], rax
0x18000da1f  cmp     dword ptr [r14], 3
0x18000da23  jnz     short loc_18000DA45
0x18000da25  mov     eax, edi
0x18000da27  inc     edi
0x18000da29  lea     rcx, [rax+rax*2]
0x18000da2d  mov     dword ptr [rsi+rcx*4], 8
0x18000da34  mov     qword ptr [rsi+rcx*4+4], 0BC9h
0x18000da3d  mov     dword ptr [r12], 8
0x18000da45  mov     rax, [rbp+arg_18]
0x18000da49  xor     ebx, ebx
0x18000da4b  mov     [rax], edi
0x18000da4d  mov     eax, ebx
0x18000da4f  jmp     short loc_18000DA84
0x18000da51  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da58  lea     rdx, WPP_GLOBAL_Control
0x18000da5f  cmp     rcx, rdx
0x18000da62  jz      short loc_18000DA7F
0x18000da64  test    byte ptr [rcx+1Ch], 1
0x18000da68  jz      short loc_18000DA7F
0x18000da6a  mov     rcx, [rcx+10h]
0x18000da6e  lea     r8, WPP_5d1fa3ffeeb63f6268e9b062752af0fc_Traceguids
0x18000da75  mov     edx, 13h
0x18000da7a  call    WPP_SF_
0x18000da7f  mov     eax, 80070057h
0x18000da84  mov     rbx, [rsp+30h+arg_0]
0x18000da89  add     rsp, 30h
0x18000da8d  pop     r15
0x18000da8f  pop     r14
0x18000da91  pop     r13
0x18000da93  pop     r12
0x18000da95  pop     rdi
0x18000da96  pop     rsi
0x18000da97  pop     rbp
0x18000da98  retn
```
