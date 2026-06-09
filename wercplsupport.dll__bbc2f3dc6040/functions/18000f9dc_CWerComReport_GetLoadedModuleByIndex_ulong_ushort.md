# CWerComReport::_GetLoadedModuleByIndex(ulong,ushort * *)

- ea: `0x18000f9dc`
- end: `0x18000fb05`
- name: `?_GetLoadedModuleByIndex@CWerComReport@@QEAAJKPEAPEAG@Z`
- size: `297`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b730`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000e35c`
- `0x18000f9dc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000faa6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000faa6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fa8f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fa8f`
- `wer!WerpGetLoadedModuleByIndex` at `0x18000fa5b`
- `wer!WerpGetLoadedModuleByIndex` at `0x18000fa5b`

## pseudocode

```c
__int64 __fastcall CWerComReport::_GetLoadedModuleByIndex(CWerComReport *this, unsigned int a2, unsigned __int16 **a3)
{
  int WerApiLock; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  OLECHAR *v9; // rcx
  unsigned __int16 *v10; // rax
  _QWORD v12[7]; // [rsp+20h] [rbp-38h] BYREF
  OLECHAR *psz; // [rsp+78h] [rbp+20h] BYREF

  psz = 0;
  v12[0] = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)v12, this);
  if ( WerApiLock >= 0 )
  {
    WerApiLock = WerpGetLoadedModuleByIndex(*((_QWORD *)this + 4), a2, &psz);
    if ( WerApiLock >= 0 )
    {
      if ( a3 && (SysFreeString(*a3), v9 = psz, *a3 = 0, v9) && (v10 = SysAllocString(v9), (*a3 = v10) == 0) )
      {
        WerApiLock = -2147024882;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
      }
      else
      {
        WerApiLock = 0;
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 69;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 68;
LABEL_5:
      WPP_SF_d(v7[2], v8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
    }
  }
  if ( v12[0] )
    _InterlockedExchange((volatile __int32 *)(v12[0] + 48LL), 0);
  return (unsigned int)WerApiLock;
}

```

## disassembly

```asm
0x18000f9dc  push    rbx
0x18000f9de  push    rbp
0x18000f9df  push    rsi
0x18000f9e0  push    rdi
0x18000f9e1  sub     rsp, 38h
0x18000f9e5  mov     ebp, edx
0x18000f9e7  mov     [rsp+58h+psz], 0
0x18000f9f0  mov     rdx, rcx; struct CWerComReport *
0x18000f9f3  mov     [rsp+58h+var_38], 0
0x18000f9fc  mov     rsi, rcx
0x18000f9ff  mov     rdi, r8
0x18000fa02  lea     rcx, [rsp+58h+var_38]; this
0x18000fa07  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x18000fa0c  mov     ebx, eax
0x18000fa0e  test    eax, eax
0x18000fa10  jns     short loc_18000FA50
0x18000fa12  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa19  lea     rax, WPP_GLOBAL_Control
0x18000fa20  cmp     rcx, rax
0x18000fa23  jz      loc_18000FAEB
0x18000fa29  test    byte ptr [rcx+1Ch], 1
0x18000fa2d  jz      loc_18000FAEB
0x18000fa33  mov     edx, 44h ; 'D'
0x18000fa38  mov     rcx, [rcx+10h]
0x18000fa3c  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000fa43  mov     r9d, ebx
0x18000fa46  call    WPP_SF_d
0x18000fa4b  jmp     loc_18000FAEB
0x18000fa50  mov     rcx, [rsi+20h]
0x18000fa54  lea     r8, [rsp+58h+psz]
0x18000fa59  mov     edx, ebp
0x18000fa5b  call    cs:__imp_WerpGetLoadedModuleByIndex
0x18000fa61  mov     ebx, eax
0x18000fa63  test    eax, eax
0x18000fa65  jns     short loc_18000FA87
0x18000fa67  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa6e  lea     rax, WPP_GLOBAL_Control
0x18000fa75  cmp     rcx, rax
0x18000fa78  jz      short loc_18000FAEB
0x18000fa7a  test    byte ptr [rcx+1Ch], 1
0x18000fa7e  jz      short loc_18000FAEB
0x18000fa80  mov     edx, 45h ; 'E'
0x18000fa85  jmp     short loc_18000FA38
0x18000fa87  test    rdi, rdi
0x18000fa8a  jz      short loc_18000FAE9
0x18000fa8c  mov     rcx, [rdi]; bstrString
0x18000fa8f  call    cs:__imp_SysFreeString
0x18000fa95  mov     rcx, [rsp+58h+psz]; psz
0x18000fa9a  mov     qword ptr [rdi], 0
0x18000faa1  test    rcx, rcx
0x18000faa4  jz      short loc_18000FAE9
0x18000faa6  call    cs:__imp_SysAllocString
0x18000faac  mov     [rdi], rax
0x18000faaf  test    rax, rax
0x18000fab2  jnz     short loc_18000FAE9
0x18000fab4  mov     ebx, 8007000Eh
0x18000fab9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fac0  lea     rax, WPP_GLOBAL_Control
0x18000fac7  cmp     rcx, rax
0x18000faca  jz      short loc_18000FAEB
0x18000facc  test    byte ptr [rcx+1Ch], 1
0x18000fad0  jz      short loc_18000FAEB
0x18000fad2  mov     rcx, [rcx+10h]
0x18000fad6  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000fadd  mov     edx, 46h ; 'F'
0x18000fae2  call    WPP_SF_
0x18000fae7  jmp     short loc_18000FAEB
0x18000fae9  xor     ebx, ebx
0x18000faeb  mov     rax, [rsp+58h+var_38]
0x18000faf0  test    rax, rax
0x18000faf3  jz      short loc_18000FAFA
0x18000faf5  xor     ecx, ecx
0x18000faf7  xchg    ecx, [rax+30h]
0x18000fafa  mov     eax, ebx
0x18000fafc  add     rsp, 38h
0x18000fb00  pop     rdi
0x18000fb01  pop     rsi
0x18000fb02  pop     rbp
0x18000fb03  pop     rbx
0x18000fb04  retn
```
