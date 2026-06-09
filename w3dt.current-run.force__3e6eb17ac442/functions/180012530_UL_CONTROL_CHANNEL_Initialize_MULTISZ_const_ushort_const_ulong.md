# UL_CONTROL_CHANNEL::Initialize(MULTISZ const &,ushort const *,ulong)

- ea: `0x180012530`
- end: `0x180012890`
- name: `?Initialize@UL_CONTROL_CHANNEL@@QEAAKAEBVMULTISZ@@PEBGK@Z`
- size: `864`
- prototype: `unsigned int __fastcall(UL_CONTROL_CHANNEL *__hidden this, const struct MULTISZ *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001060`

## callees

- `0x180012530`
- `0x180012f88`
- `0x1800130e8`
- `0x1800132cc`
- `0x180013338`
- `0x180013400`
- `0x1800134a8`
- `0x180015e08`
- `0x180015f6c`

## import_xrefs

- `HTTPAPI!HttpSetServerSessionProperty` at `0x1800125b9`
- `HTTPAPI!HttpSetServerSessionProperty` at `0x1800125b9`
- `iisutil!PuDbgPrint` at `0x180012775`
- `iisutil!PuDbgPrint` at `0x180012848`
- `iisutil!PuDbgPrint` at `0x180012885`
- `iisutil!PuDbgPrint` at `0x180012775`
- `iisutil!PuDbgPrint` at `0x180012848`
- `iisutil!PuDbgPrint` at `0x180012885`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180012589`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180012589`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800126ad`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800126ad`

## string_xrefs

- `0x180012641`: `CreateControlChannel() failed. Error = %08x. Returning\n`
- `0x18001266d`: `CreateConfigGroup failed. Error=%08x. Returning\n`
- `0x1800126f3`: `Unable to activate Config Group. Error=%08x. Returning\n`
- `0x180012736`: `CreateRequestQueue failed for AppPool '%ws'. Error=%08x. Returning\n`
- `0x180012745`: `SetConfigGroupRequestQueueHandle failed for AppPool '%ws'. Error=%08x. Returning\n`
- `0x180012764`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\controlchannel.cxx`
- `0x18001282a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\controlchannel.cxx`
- `0x180012879`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\controlchannel.cxx`

## pseudocode

```c
unsigned int __fastcall UL_CONTROL_CHANNEL::Initialize(
        HTTP_SERVER_SESSION_ID *this,
        const struct MULTISZ *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  ULONG ControlChannel; // ebx
  unsigned __int64 *v9; // r14
  unsigned int v10; // r15d
  const unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // rsi
  HTTP_SERVER_SESSION_ID v13; // rcx
  unsigned int result; // eax
  const char *v15; // rax
  __int64 v16; // r8
  unsigned int v17; // ebx
  void **v18; // rbx
  unsigned int RequestQueue; // esi
  const char *v20; // rax
  __int64 v21; // r8
  ULONG v22; // eax
  __int64 PropertyInformation; // [rsp+90h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 3) != 1 )
  {
    ControlChannel = HTTP_WRAPPER::Initialize((HTTP_WRAPPER *)this);
    if ( ControlChannel )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      {
        v15 = "Initialize() failed. Error = %08x. Returning\n";
        v16 = 82;
LABEL_42:
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\controlchannel.cxx",
          v16,
          "UL_CONTROL_CHANNEL::Initialize",
          v15,
          ControlChannel);
        return ControlChannel;
      }
      return ControlChannel;
    }
  }
  ControlChannel = HTTP_WRAPPER::CreateControlChannel((HTTP_WRAPPER *)this);
  if ( !ControlChannel )
  {
    v9 = this + 4;
    ControlChannel = HTTP_WRAPPER::CreateConfigGroup((HTTP_WRAPPER *)this, this + 4);
    if ( ControlChannel )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      {
        v15 = "CreateConfigGroup failed. Error=%08x. Returning\n";
        v16 = 122;
        goto LABEL_42;
      }
      return ControlChannel;
    }
    v10 = 1;
    v11 = MULTISZ::First(a2);
    while ( 1 )
    {
      v12 = v11;
      if ( !v11 )
        break;
      result = HTTP_WRAPPER::AddUrlToConfigGroup((HTTP_WRAPPER *)this, *v9, v11, a4, v10);
      if ( result )
        return result;
      v17 = 0;
      if ( v10 != -1 )
        v17 = v10;
      v11 = MULTISZ::Next(a2, v12);
      v10 = v17 + 1;
      if ( !v17 )
        v10 = 0;
    }
    v13 = this[2];
    PropertyInformation = 1;
    ControlChannel = HttpSetServerSessionProperty(v13, HttpServerStateProperty, &PropertyInformation, 8u);
    if ( ControlChannel )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      {
        v15 = "Unable to activate ControlChannel. Error=%08x. Returning\n";
        v16 = 180;
        goto LABEL_42;
      }
      return ControlChannel;
    }
    *((_DWORD *)this + 6) = 1;
    ControlChannel = HTTP_WRAPPER::SetConfigGroupState((HTTP_WRAPPER *)this, *v9, 1);
    if ( ControlChannel )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      {
        v15 = "Unable to activate Config Group. Error=%08x. Returning\n";
        v16 = 195;
        goto LABEL_42;
      }
      return ControlChannel;
    }
    v18 = (void **)(this + 5);
    RequestQueue = HTTP_WRAPPER::CreateRequestQueue((HTTP_WRAPPER *)this, (void **)this + 5, a3, 0);
    if ( RequestQueue )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      {
        v20 = "CreateRequestQueue failed for AppPool '%ws'. Error=%08x. Returning\n";
        v21 = 216;
LABEL_29:
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\controlchannel.cxx",
          v21,
          "UL_CONTROL_CHANNEL::Initialize",
          v20,
          a3,
          RequestQueue);
      }
    }
    else
    {
      RequestQueue = HTTP_WRAPPER::SetRequestQueueState(this, *v18, 0);
      if ( RequestQueue )
      {
        if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 8) == 0 )
          return RequestQueue;
        v20 = "SetRequestQueueState failed for AppPool '%ws'. Error=%08x. Returning\n";
        v21 = 232;
        goto LABEL_29;
      }
      RequestQueue = HTTP_WRAPPER::SetConfigGroupRequestQueueHandle((HTTP_WRAPPER *)this, *v9, *v18);
      if ( !RequestQueue )
      {
        v22 = HTTP_WRAPPER::SetRequestQueueState(this, *v18, 0);
        ControlChannel = v22;
        if ( !v22 )
          return 0;
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\controlchannel.cxx",
            272,
            "UL_CONTROL_CHANNEL::Initialize",
            "SetRequestQueueState failed for AppPool '%ws'. Error=%08x. Returning\n",
            a3,
            v22);
        return ControlChannel;
      }
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      {
        v20 = "SetConfigGroupRequestQueueHandle failed for AppPool '%ws'. Error=%08x. Returning\n";
        v21 = 252;
        goto LABEL_29;
      }
    }
    return RequestQueue;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
  {
    v15 = "CreateControlChannel() failed. Error = %08x. Returning\n";
    v16 = 102;
    goto LABEL_42;
  }
  return ControlChannel;
}

```

## disassembly

```asm
0x180012530  push    rbx
0x180012532  push    rbp
0x180012533  push    rsi
0x180012534  push    rdi
0x180012535  push    r12
0x180012537  push    r13
0x180012539  push    r14
0x18001253b  push    r15
0x18001253d  sub     rsp, 48h
0x180012541  cmp     dword ptr [rcx+0Ch], 1
0x180012545  mov     r13d, r9d
0x180012548  mov     rbp, r8
0x18001254b  mov     r12, rdx
0x18001254e  mov     rdi, rcx
0x180012551  jnz     loc_1800125F4
0x180012557  mov     rcx, rdi; this
0x18001255a  call    ?CreateControlChannel@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::CreateControlChannel(void)
0x18001255f  mov     ebx, eax
0x180012561  test    eax, eax
0x180012563  jnz     loc_18001262B
0x180012569  lea     r14, [rdi+20h]
0x18001256d  mov     rcx, rdi; this
0x180012570  mov     rdx, r14; unsigned __int64 *
0x180012573  call    ?CreateConfigGroup@HTTP_WRAPPER@@QEAAKPEA_K@Z; HTTP_WRAPPER::CreateConfigGroup(unsigned __int64 *)
0x180012578  mov     ebx, eax
0x18001257a  test    eax, eax
0x18001257c  jnz     loc_180012653
0x180012582  mov     rcx, r12
0x180012585  lea     r15d, [rax+1]
0x180012589  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x18001258f  mov     rsi, rax
0x180012592  test    rax, rax
0x180012595  jnz     loc_18001267F
0x18001259b  mov     rcx, [rdi+10h]; ServerSessionId
0x18001259f  lea     esi, [rax+1]
0x1800125a2  lea     r9d, [rax+8]; PropertyInformationLength
0x1800125a6  mov     [rsp+88h+PropertyInformation], rsi
0x1800125ae  lea     r8, [rsp+88h+PropertyInformation]; PropertyInformation
0x1800125b6  lea     edx, [rax+5]; Property
0x1800125b9  call    cs:__imp_HttpSetServerSessionProperty
0x1800125bf  mov     ebx, eax
0x1800125c1  test    eax, eax
0x1800125c3  jz      loc_1800126C2
0x1800125c9  mov     eax, cs:g_dwDebugFlags
0x1800125cf  test    al, 3
0x1800125d1  setnz   cl; this
0x1800125d4  test    al, 8
0x1800125d6  setnz   al
0x1800125d9  test    al, cl
0x1800125db  jnz     loc_18001285A
0x1800125e1  mov     eax, ebx
0x1800125e3  add     rsp, 48h
0x1800125e7  pop     r15
0x1800125e9  pop     r14
0x1800125eb  pop     r13
0x1800125ed  pop     r12
0x1800125ef  pop     rdi
0x1800125f0  pop     rsi
0x1800125f1  pop     rbp
0x1800125f2  pop     rbx
0x1800125f3  retn
0x1800125f4  call    ?Initialize@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::Initialize(void)
0x1800125f9  mov     ebx, eax
0x1800125fb  test    eax, eax
0x1800125fd  jz      loc_180012557
0x180012603  mov     ecx, cs:g_dwDebugFlags
0x180012609  test    cl, 3
0x18001260c  setnz   dl
0x18001260f  test    cl, 8
0x180012612  setnz   cl
0x180012615  test    cl, dl
0x180012617  jz      short loc_1800125E1
0x180012619  lea     rax, aInitializeFail_0; "Initialize() failed. Error = %08x. Retu"...
0x180012620  mov     r8d, 52h ; 'R'
0x180012626  jmp     loc_180012867
0x18001262b  mov     ecx, cs:g_dwDebugFlags
0x180012631  test    cl, 3
0x180012634  setnz   dl
0x180012637  test    cl, 8
0x18001263a  setnz   cl
0x18001263d  test    cl, dl
0x18001263f  jz      short loc_1800125E1
0x180012641  lea     rax, aCreatecontrolc; "CreateControlChannel() failed. Error = "...
0x180012648  mov     r8d, 66h ; 'f'
0x18001264e  jmp     loc_180012867
0x180012653  mov     ecx, cs:g_dwDebugFlags
0x180012659  test    cl, 3
0x18001265c  setnz   dl
0x18001265f  test    cl, 8
0x180012662  setnz   cl
0x180012665  test    cl, dl
0x180012667  jz      loc_1800125E1
0x18001266d  lea     rax, aCreateconfiggr; "CreateConfigGroup failed. Error=%08x. R"...
0x180012674  mov     r8d, 7Ah ; 'z'
0x18001267a  jmp     loc_180012867
0x18001267f  mov     rdx, [r14]; unsigned __int64
0x180012682  mov     r9d, r13d; unsigned int
0x180012685  mov     r8, rsi; unsigned __int16 *
0x180012688  mov     [rsp+88h+var_68], r15d; unsigned int
0x18001268d  mov     rcx, rdi; this
0x180012690  call    ?AddUrlToConfigGroup@HTTP_WRAPPER@@QEAAK_KPEBGKK@Z; HTTP_WRAPPER::AddUrlToConfigGroup(unsigned __int64,ushort const *,ulong,ulong)
0x180012695  test    eax, eax
0x180012697  jnz     loc_1800125E3
0x18001269d  xor     ebx, ebx
0x18001269f  mov     rdx, rsi
0x1800126a2  cmp     r15d, 0FFFFFFFFh
0x1800126a6  mov     rcx, r12
0x1800126a9  cmovnz  ebx, r15d
0x1800126ad  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x1800126b3  test    ebx, ebx
0x1800126b5  lea     r15d, [rbx+1]
0x1800126b9  cmovz   r15d, ebx
0x1800126bd  jmp     loc_18001258F
0x1800126c2  mov     [rdi+18h], esi
0x1800126c5  mov     r8d, esi; int
0x1800126c8  mov     rdx, [r14]; unsigned __int64
0x1800126cb  mov     rcx, rdi; this
0x1800126ce  call    ?SetConfigGroupState@HTTP_WRAPPER@@QEAAK_KH@Z; HTTP_WRAPPER::SetConfigGroupState(unsigned __int64,int)
0x1800126d3  mov     ebx, eax
0x1800126d5  test    eax, eax
0x1800126d7  jz      short loc_180012705
0x1800126d9  mov     ecx, cs:g_dwDebugFlags
0x1800126df  test    cl, 3
0x1800126e2  setnz   dl
0x1800126e5  test    cl, 8
0x1800126e8  setnz   cl
0x1800126eb  test    cl, dl
0x1800126ed  jz      loc_1800125E1
0x1800126f3  lea     rax, aUnableToActiva; "Unable to activate Config Group. Error="...
0x1800126fa  mov     r8d, 0C3h
0x180012700  jmp     loc_180012867
0x180012705  lea     rbx, [rdi+28h]
0x180012709  xor     r9d, r9d; struct _SECURITY_ATTRIBUTES *
0x18001270c  mov     rdx, rbx; void **
0x18001270f  mov     r8, rbp; unsigned __int16 *
0x180012712  mov     rcx, rdi; this
0x180012715  call    ?CreateRequestQueue@HTTP_WRAPPER@@QEAAKPEAPEAXPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; HTTP_WRAPPER::CreateRequestQueue(void * *,ushort const *,_SECURITY_ATTRIBUTES *)
0x18001271a  mov     esi, eax
0x18001271c  test    eax, eax
0x18001271e  jz      short loc_180012782
0x180012720  mov     ecx, cs:g_dwDebugFlags
0x180012726  test    cl, 3
0x180012729  setnz   dl
0x18001272c  test    cl, 8
0x18001272f  setnz   cl
0x180012732  test    cl, dl
0x180012734  jz      short loc_18001277B
0x180012736  lea     rax, aCreaterequestq; "CreateRequestQueue failed for AppPool '"...
0x18001273d  mov     r8d, 0D8h
0x180012743  jmp     short loc_180012752
0x180012745  lea     rax, aSetconfiggroup; "SetConfigGroupRequestQueueHandle failed"...
0x18001274c  mov     r8d, 0FCh
0x180012752  mov     rcx, cs:g_pDebug
0x180012759  lea     r9, aUlControlChann; "UL_CONTROL_CHANNEL::Initialize"
0x180012760  mov     [rsp+88h+var_58], esi
0x180012764  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001276b  mov     [rsp+88h+var_60], rbp
0x180012770  mov     qword ptr [rsp+88h+var_68], rax
0x180012775  call    cs:__imp_PuDbgPrint
0x18001277b  mov     eax, esi
0x18001277d  jmp     loc_1800125E3
0x180012782  mov     rdx, [rbx]
0x180012785  xor     r8d, r8d
0x180012788  mov     rcx, rdi
0x18001278b  call    ?SetRequestQueueState@HTTP_WRAPPER@@QEAAKPEAXW4HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON@@@Z; HTTP_WRAPPER::SetRequestQueueState(void *,HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON)
0x180012790  mov     esi, eax
0x180012792  test    eax, eax
0x180012794  jz      short loc_1800127BB
0x180012796  mov     ecx, cs:g_dwDebugFlags
0x18001279c  test    cl, 3
0x18001279f  setnz   dl
0x1800127a2  test    cl, 8
0x1800127a5  setnz   cl
0x1800127a8  test    cl, dl
0x1800127aa  jz      short loc_18001277B
0x1800127ac  lea     rax, aSetrequestqueu; "SetRequestQueueState failed for AppPool"...
0x1800127b3  mov     r8d, 0E8h
0x1800127b9  jmp     short loc_180012752
0x1800127bb  mov     r8, [rbx]; void *
0x1800127be  mov     rcx, rdi; this
0x1800127c1  mov     rdx, [r14]; unsigned __int64
0x1800127c4  call    ?SetConfigGroupRequestQueueHandle@HTTP_WRAPPER@@QEAAK_KPEAX@Z; HTTP_WRAPPER::SetConfigGroupRequestQueueHandle(unsigned __int64,void *)
0x1800127c9  mov     esi, eax
0x1800127cb  test    eax, eax
0x1800127cd  jz      short loc_1800127EA
0x1800127cf  mov     ecx, cs:g_dwDebugFlags
0x1800127d5  test    cl, 3
0x1800127d8  setnz   dl
0x1800127db  test    cl, 8
0x1800127de  setnz   cl
0x1800127e1  test    cl, dl
0x1800127e3  jz      short loc_18001277B
0x1800127e5  jmp     loc_180012745
0x1800127ea  mov     rdx, [rbx]
0x1800127ed  xor     r8d, r8d
0x1800127f0  mov     rcx, rdi
0x1800127f3  call    ?SetRequestQueueState@HTTP_WRAPPER@@QEAAKPEAXW4HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON@@@Z; HTTP_WRAPPER::SetRequestQueueState(void *,HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON)
0x1800127f8  mov     ebx, eax
0x1800127fa  test    eax, eax
0x1800127fc  jz      short loc_180012853
0x1800127fe  mov     ecx, cs:g_dwDebugFlags
0x180012804  test    cl, 3
0x180012807  setnz   dl
0x18001280a  test    cl, 8
0x18001280d  setnz   cl
0x180012810  test    cl, dl
0x180012812  jz      loc_1800125E1
0x180012818  mov     rcx, cs:g_pDebug
0x18001281f  lea     r9, aUlControlChann; "UL_CONTROL_CHANNEL::Initialize"
0x180012826  mov     [rsp+88h+var_58], eax
0x18001282a  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180012831  lea     rax, aSetrequestqueu; "SetRequestQueueState failed for AppPool"...
0x180012838  mov     [rsp+88h+var_60], rbp
0x18001283d  mov     r8d, 110h
0x180012843  mov     qword ptr [rsp+88h+var_68], rax
0x180012848  call    cs:__imp_PuDbgPrint
0x18001284e  jmp     loc_1800125E1
0x180012853  xor     eax, eax
0x180012855  jmp     loc_1800125E3
0x18001285a  lea     rax, aUnableToActiva_0; "Unable to activate ControlChannel. Erro"...
0x180012861  mov     r8d, 0B4h
0x180012867  mov     rcx, cs:g_pDebug
0x18001286e  lea     r9, aUlControlChann; "UL_CONTROL_CHANNEL::Initialize"
0x180012875  mov     dword ptr [rsp+88h+var_60], ebx
0x180012879  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180012880  mov     qword ptr [rsp+88h+var_68], rax
0x180012885  call    cs:__imp_PuDbgPrint
0x18001288b  jmp     loc_1800125E1
```
