# DiagPackage::AddXmlToReport(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x180014544`
- end: `0x180014833`
- name: `?AddXmlToReport@DiagPackage@@QEAAJPEAG000000@Z`
- size: `751`
- prototype: `__int64 __fastcall(struct Settings **this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, wchar_t *String2, wchar_t *String1, wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18000a000`
- `0x18000a2f4`

## callees

- `0x180004d58`
- `0x180014438`
- `0x180014544`
- `0x180018718`
- `0x180026fa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800145cb`
- `msvcrt!_wcsicmp` at `0x1800146d7`
- `msvcrt!_wcsicmp` at `0x1800145cb`
- `msvcrt!_wcsicmp` at `0x1800146d7`

## string_xrefs

- `0x180014804`: `DiagPackage::AddXmlToReport`

## pseudocode

```c
__int64 __fastcall DiagPackage::AddXmlToReport(
        struct Settings **this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        wchar_t *String2,
        wchar_t *String1,
        wchar_t *a8)
{
  int v12; // r8d
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // r9d
  struct Settings *v16; // rcx
  int v17; // ecx
  int v18; // ecx
  Rootcause *v19; // rcx
  int v20; // eax
  struct IXMLDOMDocument2 *v21; // rdx
  int updated; // eax
  Rootcause *v23; // rcx
  int v24; // eax
  __int64 v25; // rsi
  int v26; // eax

  if ( !a2 )
  {
    v12 = 2194;
LABEL_44:
    v15 = -2147024809;
    goto LABEL_45;
  }
  if ( !a3 )
  {
    v12 = 2195;
    goto LABEL_44;
  }
  if ( !a4 )
  {
    v12 = 2196;
    goto LABEL_44;
  }
  if ( !a5 )
  {
    v12 = 2197;
    goto LABEL_44;
  }
  if ( !String2 )
  {
    v12 = 2198;
    goto LABEL_44;
  }
  if ( !_wcsicmp(L"Debug", String2) )
  {
    v13 = DiagPackage::AddXmlToDebugReport((DiagPackage *)this, a2, a3, a4, a5);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = v13;
      v12 = 2205;
LABEL_46:
      SdpDebugTrace(1u, L"DiagPackage::AddXmlToReport", v12, v15);
      return v14;
    }
    return v14;
  }
  v16 = this[1];
  if ( !v16 )
  {
    v15 = -2147467261;
    v12 = 2210;
    goto LABEL_45;
  }
  v14 = 0;
  v17 = *((_DWORD *)v16 + 22) - 3;
  if ( v17 )
  {
    v18 = v17 - 2;
    if ( v18 )
    {
      if ( v18 != 1 )
      {
        v12 = 2285;
        goto LABEL_44;
      }
      return v14;
    }
    v19 = this[12];
    if ( !v19 )
    {
      v15 = -2147467261;
      v12 = 2263;
      goto LABEL_45;
    }
    v20 = Rootcause::AddXmlToReport(v19, a2, a3, a4, a5, String2, String1, a8);
    v14 = v20;
    if ( v20 < 0 )
    {
      v15 = v20;
      v12 = 2271;
      goto LABEL_46;
    }
    if ( v20 == 1 || !this[12] )
    {
      v15 = -2147467259;
      v12 = 2272;
      goto LABEL_45;
    }
  }
  else
  {
    if ( !_wcsicmp(String1, &word_18002DFCC) )
    {
      v21 = (struct IXMLDOMDocument2 *)this[16];
      if ( v21 )
      {
        updated = SdpUpdateReportData(this[1], v21, a5, a2, a3, a4, String2);
        v14 = updated;
        if ( updated < 0 )
        {
          v15 = updated;
          v12 = 2229;
          goto LABEL_46;
        }
        return v14;
      }
      v15 = -2147467261;
      v12 = 2221;
LABEL_45:
      v14 = v15;
      goto LABEL_46;
    }
    v23 = this[12];
    if ( !v23 )
    {
      v25 = 0;
      if ( *((_DWORD *)this + 8) )
      {
        while ( 1 )
        {
          v26 = Rootcause::AddXmlToReport(
                  (struct Settings *)((char *)this[3] + 144 * v25),
                  a2,
                  a3,
                  a4,
                  a5,
                  String2,
                  String1,
                  a8);
          v14 = v26;
          if ( v26 < 0 )
            break;
          if ( v26 == 1 )
          {
            v25 = (unsigned int)(v25 + 1);
            if ( (unsigned int)v25 < *((_DWORD *)this + 8) )
              continue;
          }
          goto LABEL_42;
        }
        v15 = v26;
        v12 = 2251;
        goto LABEL_46;
      }
LABEL_42:
      if ( (unsigned int)v25 >= *((_DWORD *)this + 8) )
      {
        v12 = 2256;
        goto LABEL_44;
      }
      return v14;
    }
    v24 = Rootcause::AddXmlToReport(v23, a2, a3, a4, a5, String2, String1, a8);
    v14 = v24;
    if ( v24 < 0 )
    {
      v15 = v24;
      v12 = 2239;
      goto LABEL_46;
    }
    if ( v24 == 1 || !this[12] )
    {
      v15 = -2147467259;
      v12 = 2240;
      goto LABEL_45;
    }
  }
  return v14;
}

```

## disassembly

```asm
0x180014544  push    rbx
0x180014546  push    rbp
0x180014547  push    rsi
0x180014548  push    rdi
0x180014549  push    r12
0x18001454b  push    r13
0x18001454d  push    r14
0x18001454f  push    r15
0x180014551  sub     rsp, 48h
0x180014555  mov     r15, r9
0x180014558  mov     r12, r8
0x18001455b  mov     r13, rdx
0x18001455e  mov     rdi, rcx
0x180014561  test    rdx, rdx
0x180014564  jnz     short loc_180014571
0x180014566  mov     r8d, 892h
0x18001456c  jmp     loc_1800147FB
0x180014571  test    r12, r12
0x180014574  jnz     short loc_180014581
0x180014576  mov     r8d, 893h
0x18001457c  jmp     loc_1800147FB
0x180014581  test    r15, r15
0x180014584  jnz     short loc_180014591
0x180014586  mov     r8d, 894h
0x18001458c  jmp     loc_1800147FB
0x180014591  mov     r14, [rsp+88h+arg_20]
0x180014599  test    r14, r14
0x18001459c  jnz     short loc_1800145A9
0x18001459e  mov     r8d, 895h
0x1800145a4  jmp     loc_1800147FB
0x1800145a9  mov     rbp, [rsp+88h+String2]
0x1800145b1  test    rbp, rbp
0x1800145b4  jnz     short loc_1800145C1
0x1800145b6  mov     r8d, 896h
0x1800145bc  jmp     loc_1800147FB
0x1800145c1  mov     rdx, rbp; String2
0x1800145c4  lea     rcx, aDebug; "Debug"
0x1800145cb  call    cs:__imp__wcsicmp
0x1800145d1  test    eax, eax
0x1800145d3  jnz     short loc_180014603
0x1800145d5  mov     r9, r15; unsigned __int16 *
0x1800145d8  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x1800145dd  mov     r8, r12; unsigned __int16 *
0x1800145e0  mov     rdx, r13; unsigned __int16 *
0x1800145e3  mov     rcx, rdi; this
0x1800145e6  call    ?AddXmlToDebugReport@DiagPackage@@QEAAJPEAG000@Z; DiagPackage::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)
0x1800145eb  mov     ebx, eax
0x1800145ed  test    eax, eax
0x1800145ef  jns     loc_180014815
0x1800145f5  mov     r9d, eax
0x1800145f8  mov     r8d, 89Dh
0x1800145fe  jmp     loc_180014804
0x180014603  mov     rcx, [rdi+8]
0x180014607  test    rcx, rcx
0x18001460a  jnz     short loc_18001461D
0x18001460c  mov     r9d, 80004003h
0x180014612  mov     r8d, 8A2h
0x180014618  jmp     loc_180014801
0x18001461d  mov     ecx, [rcx+58h]
0x180014620  xor     ebx, ebx
0x180014622  sub     ecx, 3
0x180014625  jz      loc_1800146C5
0x18001462b  sub     ecx, 2
0x18001462e  jz      short loc_180014644
0x180014630  cmp     ecx, 1
0x180014633  jz      loc_180014815
0x180014639  mov     r8d, 8EDh
0x18001463f  jmp     loc_1800147FB
0x180014644  mov     rcx, [rdi+60h]; this
0x180014648  test    rcx, rcx
0x18001464b  jnz     short loc_18001465E
0x18001464d  mov     r9d, 80004003h
0x180014653  mov     r8d, 8D7h
0x180014659  jmp     loc_180014801
0x18001465e  mov     rax, [rsp+88h+arg_38]
0x180014666  mov     r9, r15; unsigned __int16 *
0x180014669  mov     [rsp+88h+var_50], rax; wchar_t *
0x18001466e  mov     r8, r12; unsigned __int16 *
0x180014671  mov     rax, [rsp+88h+String1]
0x180014679  mov     rdx, r13; unsigned __int16 *
0x18001467c  mov     [rsp+88h+var_58], rax; String1
0x180014681  mov     [rsp+88h+var_60], rbp; unsigned __int16 *
0x180014686  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x18001468b  call    ?AddXmlToReport@Rootcause@@QEAAJPEAG000000@Z; Rootcause::AddXmlToReport(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x180014690  mov     ebx, eax
0x180014692  test    eax, eax
0x180014694  jns     short loc_1800146A4
0x180014696  mov     r9d, eax
0x180014699  mov     r8d, 8DFh
0x18001469f  jmp     loc_180014804
0x1800146a4  cmp     eax, 1
0x1800146a7  jz      short loc_1800146B4
0x1800146a9  cmp     qword ptr [rdi+60h], 0
0x1800146ae  jnz     loc_180014815
0x1800146b4  mov     r9d, 80004005h
0x1800146ba  mov     r8d, 8E0h
0x1800146c0  jmp     loc_180014801
0x1800146c5  mov     rsi, [rsp+88h+String1]
0x1800146cd  lea     rdx, word_18002DFCC; String2
0x1800146d4  mov     rcx, rsi; String1
0x1800146d7  call    cs:__imp__wcsicmp
0x1800146dd  test    eax, eax
0x1800146df  jnz     short loc_180014734
0x1800146e1  mov     rdx, [rdi+80h]; struct IXMLDOMDocument2 *
0x1800146e8  test    rdx, rdx
0x1800146eb  jnz     short loc_1800146FE
0x1800146ed  mov     r9d, 80004003h
0x1800146f3  mov     r8d, 8ADh
0x1800146f9  jmp     loc_180014801
0x1800146fe  mov     rcx, [rdi+8]; struct Settings *
0x180014702  mov     r9, r13; unsigned __int16 *
0x180014705  mov     [rsp+88h+var_58], rbp; unsigned __int16 *
0x18001470a  mov     r8, r14; unsigned __int16 *
0x18001470d  mov     [rsp+88h+var_60], r15; unsigned __int16 *
0x180014712  mov     [rsp+88h+var_68], r12; unsigned __int16 *
0x180014717  call    ?SdpUpdateReportData@@YAJPEAVSettings@@PEAUIXMLDOMDocument2@@PEAG2222@Z; SdpUpdateReportData(Settings *,IXMLDOMDocument2 *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18001471c  mov     ebx, eax
0x18001471e  test    eax, eax
0x180014720  jns     loc_180014815
0x180014726  mov     r9d, eax
0x180014729  mov     r8d, 8B5h
0x18001472f  jmp     loc_180014804
0x180014734  mov     rcx, [rdi+60h]; this
0x180014738  test    rcx, rcx
0x18001473b  jz      short loc_180014799
0x18001473d  mov     rax, [rsp+88h+arg_38]
0x180014745  mov     r9, r15; unsigned __int16 *
0x180014748  mov     [rsp+88h+var_50], rax; wchar_t *
0x18001474d  mov     r8, r12; unsigned __int16 *
0x180014750  mov     [rsp+88h+var_58], rsi; String1
0x180014755  mov     rdx, r13; unsigned __int16 *
0x180014758  mov     [rsp+88h+var_60], rbp; unsigned __int16 *
0x18001475d  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x180014762  call    ?AddXmlToReport@Rootcause@@QEAAJPEAG000000@Z; Rootcause::AddXmlToReport(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x180014767  mov     ebx, eax
0x180014769  test    eax, eax
0x18001476b  jns     short loc_18001477B
0x18001476d  mov     r9d, eax
0x180014770  mov     r8d, 8BFh
0x180014776  jmp     loc_180014804
0x18001477b  cmp     eax, 1
0x18001477e  jz      short loc_18001478B
0x180014780  cmp     qword ptr [rdi+60h], 0
0x180014785  jnz     loc_180014815
0x18001478b  mov     r9d, 80004005h
0x180014791  mov     r8d, 8C0h
0x180014797  jmp     short loc_180014801
0x180014799  xor     esi, esi
0x18001479b  cmp     [rdi+20h], ebx
0x18001479e  jbe     short loc_1800147F0
0x1800147a0  mov     rax, [rsp+88h+arg_38]
0x1800147a8  lea     rcx, [rsi+rsi*8]
0x1800147ac  mov     [rsp+88h+var_50], rax; wchar_t *
0x1800147b1  mov     r9, r15; unsigned __int16 *
0x1800147b4  mov     rax, [rsp+88h+String1]
0x1800147bc  mov     r8, r12; unsigned __int16 *
0x1800147bf  mov     [rsp+88h+var_58], rax; String1
0x1800147c4  mov     rdx, r13; unsigned __int16 *
0x1800147c7  shl     rcx, 4
0x1800147cb  add     rcx, [rdi+18h]; this
0x1800147cf  mov     [rsp+88h+var_60], rbp; unsigned __int16 *
0x1800147d4  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x1800147d9  call    ?AddXmlToReport@Rootcause@@QEAAJPEAG000000@Z; Rootcause::AddXmlToReport(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x1800147de  mov     ebx, eax
0x1800147e0  test    eax, eax
0x1800147e2  js      short loc_180014828
0x1800147e4  cmp     eax, 1
0x1800147e7  jnz     short loc_1800147F0
0x1800147e9  inc     esi
0x1800147eb  cmp     esi, [rdi+20h]
0x1800147ee  jb      short loc_1800147A0
0x1800147f0  cmp     esi, [rdi+20h]
0x1800147f3  jb      short loc_180014815
0x1800147f5  mov     r8d, 8D0h; int
0x1800147fb  mov     r9d, 80070057h; int
0x180014801  mov     ebx, r9d
0x180014804  lea     rdx, aDiagpackageAdd_0; "DiagPackage::AddXmlToReport"
0x18001480b  mov     ecx, 1; Level
0x180014810  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180014815  mov     eax, ebx
0x180014817  add     rsp, 48h
0x18001481b  pop     r15
0x18001481d  pop     r14
0x18001481f  pop     r13
0x180014821  pop     r12
0x180014823  pop     rdi
0x180014824  pop     rsi
0x180014825  pop     rbp
0x180014826  pop     rbx
0x180014827  retn
0x180014828  mov     r9d, eax
0x18001482b  mov     r8d, 8CBh
0x180014831  jmp     short loc_180014804
```
