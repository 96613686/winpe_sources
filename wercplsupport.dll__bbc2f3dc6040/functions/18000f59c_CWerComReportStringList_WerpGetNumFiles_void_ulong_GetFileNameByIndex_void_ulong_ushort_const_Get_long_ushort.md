# CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&GetFileNameByIndex(void *,ulong,ushort const * *)>::_Get(long,ushort * *)

- ea: `0x18000f59c`
- end: `0x18000f6c2`
- name: `?_Get@?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?GetFileNameByIndex@@YAJ0KPEAPEBG@Z@@QEAAJJPEAPEAG@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, unsigned int, BSTR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000af40`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000b5e8`
- `0x18000e35c`
- `0x18000f59c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f668`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f668`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f65d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f65d`

## pseudocode

```c
__int64 __fastcall CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long GetFileNameByIndex(void *,unsigned long,unsigned short const * *)>::_Get(
        __int64 a1,
        unsigned int a2,
        BSTR *a3)
{
  struct CWerComReport *v4; // rdx
  int WerApiLock; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  BSTR v11; // rax
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp+20h] BYREF

  psz = 0;
  v4 = *(struct CWerComReport **)(a1 + 40);
  v12 = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v12, v4);
  if ( WerApiLock < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 14;
LABEL_5:
      WPP_SF_d(v8[2], v9, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  WerApiLock = GetFileNameByIndex(*(void **)(a1 + 32), a2, (const unsigned __int16 **)&psz);
  if ( WerApiLock < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 15;
      goto LABEL_5;
    }
LABEL_6:
    if ( v12 )
      _InterlockedExchange((volatile __int32 *)(v12 + 48), 0);
    return (unsigned int)WerApiLock;
  }
  SysFreeString(*a3);
  v11 = SysAllocString(psz);
  *a3 = v11;
  if ( v11 || !psz )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
  if ( v12 )
    _InterlockedExchange((volatile __int32 *)(v12 + 48), 0);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000f59c  mov     rax, rsp
0x18000f59f  mov     [rax+10h], rbx
0x18000f5a3  push    rbp
0x18000f5a4  push    rsi
0x18000f5a5  push    rdi
0x18000f5a6  sub     rsp, 20h
0x18000f5aa  mov     ebp, edx
0x18000f5ac  mov     qword ptr [rax+20h], 0
0x18000f5b4  mov     rdx, [rcx+28h]; struct CWerComReport *
0x18000f5b8  mov     rsi, rcx
0x18000f5bb  lea     rcx, [rax+8]; this
0x18000f5bf  mov     qword ptr [rax+8], 0
0x18000f5c7  mov     rdi, r8
0x18000f5ca  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x18000f5cf  mov     ebx, eax
0x18000f5d1  test    eax, eax
0x18000f5d3  jns     short loc_18000F624
0x18000f5d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5dc  lea     rdx, WPP_GLOBAL_Control
0x18000f5e3  cmp     rcx, rdx
0x18000f5e6  jz      short loc_18000F606
0x18000f5e8  test    byte ptr [rcx+1Ch], 1
0x18000f5ec  jz      short loc_18000F606
0x18000f5ee  mov     edx, 0Eh
0x18000f5f3  mov     rcx, [rcx+10h]
0x18000f5f7  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f5fe  mov     r9d, ebx
0x18000f601  call    WPP_SF_d
0x18000f606  mov     rax, [rsp+38h+arg_0]
0x18000f60b  test    rax, rax
0x18000f60e  jz      short loc_18000F615
0x18000f610  xor     ecx, ecx
0x18000f612  xchg    ecx, [rax+30h]
0x18000f615  mov     eax, ebx
0x18000f617  mov     rbx, [rsp+38h+arg_8]
0x18000f61c  add     rsp, 20h
0x18000f620  pop     rdi
0x18000f621  pop     rsi
0x18000f622  pop     rbp
0x18000f623  retn
0x18000f624  mov     rcx, [rsi+20h]; void *
0x18000f628  lea     r8, [rsp+38h+psz]; unsigned __int16 **
0x18000f62d  mov     edx, ebp; unsigned int
0x18000f62f  call    ?GetFileNameByIndex@@YAJPEAXKPEAPEBG@Z; GetFileNameByIndex(void *,ulong,ushort const * *)
0x18000f634  mov     ebx, eax
0x18000f636  test    eax, eax
0x18000f638  jns     short loc_18000F65A
0x18000f63a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f641  lea     rdx, WPP_GLOBAL_Control
0x18000f648  cmp     rcx, rdx
0x18000f64b  jz      short loc_18000F606
0x18000f64d  test    byte ptr [rcx+1Ch], 1
0x18000f651  jz      short loc_18000F606
0x18000f653  mov     edx, 0Fh
0x18000f658  jmp     short loc_18000F5F3
0x18000f65a  mov     rcx, [rdi]; bstrString
0x18000f65d  call    cs:__imp_SysFreeString
0x18000f663  mov     rcx, [rsp+38h+psz]; psz
0x18000f668  call    cs:__imp_SysAllocString
0x18000f66e  mov     [rdi], rax
0x18000f671  test    rax, rax
0x18000f674  jnz     short loc_18000F606
0x18000f676  cmp     [rsp+38h+psz], rax
0x18000f67b  jz      short loc_18000F606
0x18000f67d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f684  lea     rdx, WPP_GLOBAL_Control
0x18000f68b  cmp     rcx, rdx
0x18000f68e  jz      short loc_18000F6A9
0x18000f690  test    byte ptr [rcx+1Ch], 1
0x18000f694  jz      short loc_18000F6A9
0x18000f696  mov     rcx, [rcx+10h]
0x18000f69a  lea     edx, [rax+10h]
0x18000f69d  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f6a4  call    WPP_SF_
0x18000f6a9  mov     rax, [rsp+38h+arg_0]
0x18000f6ae  test    rax, rax
0x18000f6b1  jz      short loc_18000F6B8
0x18000f6b3  xor     ecx, ecx
0x18000f6b5  xchg    ecx, [rax+30h]
0x18000f6b8  mov     eax, 8007000Eh
0x18000f6bd  jmp     loc_18000F617
```
