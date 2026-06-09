# IASPolicy::InternalRemove(void)

- ea: `0x1800357c0`
- end: `0x180035958`
- name: `?InternalRemove@IASPolicy@@UEAAJXZ`
- size: `408`
- prototype: `__int64 __fastcall(IASPolicy *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180024cac`
- `0x180027e60`
- `0x18002cd00`
- `0x180034f44`
- `0x1800357c0`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x1800358ff`: `pProfiles->Remove failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASPolicy::InternalRemove(IASPolicy *this)
{
  unsigned int v2; // edx
  int SdoCollection; // ebx
  int v4; // edx
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  struct ISdoCollection *v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  v6 = 0;
  v2 = 1026;
  if ( *((_DWORD *)this + 28) != 9 )
    v2 = 1031;
  SdoCollection = GetSdoCollection(*((struct ISdo **)this + 4), v2, &v7);
  if ( SdoCollection >= 0 )
  {
    if ( *((_QWORD *)this + 15)
      || (SdoCollection = IASPolicy::GetProfileObject((IASPolicy *)((char *)this - 8)), SdoCollection >= 0) )
    {
      (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 15))(*((_QWORD *)this + 15), &IID_IDispatch, &v6);
      SdoCollection = ((__int64 (__fastcall *)(struct ISdoCollection *, __int64))v7->lpVtbl->Remove)(v7, v6);
      if ( SdoCollection < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("pProfiles->Remove failed with 0x%x");
        v4 = 60;
        goto LABEL_19;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("GetProfileObject failed with 0x%x");
      v4 = 59;
      goto LABEL_19;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("Could not get the profiles collection: 0x%x");
    v4 = 58;
LABEL_19:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      (unsigned int)WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids,
      (unsigned int)"NPSSDO",
      SdoCollection);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  return (unsigned int)SdoCollection;
}

```

## disassembly

```asm
0x1800357c0  mov     r11, rsp
0x1800357c3  mov     [r11+18h], rbx
0x1800357c7  mov     [r11+20h], rsi
0x1800357cb  push    rdi
0x1800357cc  sub     rsp, 30h
0x1800357d0  mov     rdi, rcx
0x1800357d3  mov     qword ptr [r11+10h], 0
0x1800357db  mov     qword ptr [r11+8], 0
0x1800357e3  mov     edx, 402h
0x1800357e8  lea     eax, [rdx+5]
0x1800357eb  cmp     dword ptr [rcx+70h], 9
0x1800357ef  cmovnz  edx, eax; unsigned int
0x1800357f2  lea     r8, [r11+10h]; struct ISdoCollection **
0x1800357f6  mov     rcx, [rcx+20h]; struct ISdo *
0x1800357fa  call    ?GetSdoCollection@@YAJPEAUISdo@@KPEAPEAUISdoCollection@@@Z; GetSdoCollection(ISdo *,ulong,ISdoCollection * *)
0x1800357ff  mov     ebx, eax
0x180035801  test    eax, eax
0x180035803  jns     short loc_18003584B
0x180035805  lea     rax, WPP_GLOBAL_Control
0x18003580c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035813  cmp     rcx, rax
0x180035816  jz      loc_180035932
0x18003581c  cmp     byte ptr [rcx+19h], 2
0x180035820  jb      loc_180035932
0x180035826  test    dword ptr [rcx+1Ch], 400h
0x18003582d  jz      loc_180035932
0x180035833  mov     edx, ebx
0x180035835  lea     rcx, aCouldNotGetThe; "Could not get the profiles collection: "...
0x18003583c  call    WppDbgPrint
0x180035841  mov     edx, 3Ah ; ':'
0x180035846  jmp     loc_180035910
0x18003584b  cmp     qword ptr [rdi+78h], 0
0x180035850  jnz     short loc_1800358A4
0x180035852  lea     rcx, [rdi-8]; this
0x180035856  call    ?GetProfileObject@IASPolicy@@QEAAJXZ; IASPolicy::GetProfileObject(void)
0x18003585b  mov     ebx, eax
0x18003585d  test    eax, eax
0x18003585f  jns     short loc_1800358A4
0x180035861  lea     rax, WPP_GLOBAL_Control
0x180035868  mov     rcx, cs:WPP_GLOBAL_Control
0x18003586f  cmp     rcx, rax
0x180035872  jz      loc_180035932
0x180035878  cmp     byte ptr [rcx+19h], 2
0x18003587c  jb      loc_180035932
0x180035882  test    dword ptr [rcx+1Ch], 400h
0x180035889  jz      loc_180035932
0x18003588f  mov     edx, ebx
0x180035891  lea     rcx, aGetprofileobje; "GetProfileObject failed with 0x%x"
0x180035898  call    WppDbgPrint
0x18003589d  mov     edx, 3Bh ; ';'
0x1800358a2  jmp     short loc_180035910
0x1800358a4  mov     rcx, [rdi+78h]
0x1800358a8  mov     rax, [rcx]
0x1800358ab  lea     r8, [rsp+38h+arg_0]
0x1800358b0  lea     rdx, IID_IDispatch
0x1800358b7  mov     rax, [rax]
0x1800358ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358bf  mov     rcx, [rsp+38h+arg_8]
0x1800358c4  mov     rax, [rcx]
0x1800358c7  mov     rdx, [rsp+38h+arg_0]
0x1800358cc  mov     rax, [rax+48h]
0x1800358d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358d5  mov     ebx, eax
0x1800358d7  test    eax, eax
0x1800358d9  jns     short loc_180035932
0x1800358db  lea     rax, WPP_GLOBAL_Control
0x1800358e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358e9  cmp     rcx, rax
0x1800358ec  jz      short loc_180035932
0x1800358ee  cmp     byte ptr [rcx+19h], 2
0x1800358f2  jb      short loc_180035932
0x1800358f4  test    dword ptr [rcx+1Ch], 400h
0x1800358fb  jz      short loc_180035932
0x1800358fd  mov     edx, ebx
0x1800358ff  lea     rcx, aPprofilesRemov; "pProfiles->Remove failed with 0x%x"
0x180035906  call    WppDbgPrint
0x18003590b  mov     edx, 3Ch ; '<'
0x180035910  mov     rcx, cs:WPP_GLOBAL_Control
0x180035917  mov     [rsp+38h+var_18], ebx
0x18003591b  lea     r9, aNpssdo; "NPSSDO"
0x180035922  lea     r8, WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids
0x180035929  mov     rcx, [rcx+10h]
0x18003592d  call    WPP_SF_sd
0x180035932  lea     rcx, [rsp+38h+arg_0]
0x180035937  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003593c  lea     rcx, [rsp+38h+arg_8]
0x180035941  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180035946  mov     eax, ebx
0x180035948  mov     rbx, [rsp+38h+arg_10]
0x18003594d  mov     rsi, [rsp+38h+arg_18]
0x180035952  add     rsp, 30h
0x180035956  pop     rdi
0x180035957  retn
```
