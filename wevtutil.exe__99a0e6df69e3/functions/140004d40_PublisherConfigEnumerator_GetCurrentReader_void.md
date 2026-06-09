# PublisherConfigEnumerator::GetCurrentReader(void)

- ea: `0x140004d40`
- end: `0x140004eac`
- name: `?GetCurrentReader@PublisherConfigEnumerator@@QEAA?AV?$unique_ptr@VPublisherConfigReader@@U?$default_delete@VPublisherConfigReader@@@utl@@@utl@@XZ`
- size: `364`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000a6a0`
- `0x14000adf0`

## callees

- `0x140004d40`
- `0x140004ec0`
- `0x1400050a0`
- `0x140021b00`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004d8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004d8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004d9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004d9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall PublisherConfigEnumerator::GetCurrentReader(__int64 a1, _QWORD *a2)
{
  const char *v4; // r8
  HANDLE ProcessHeap; // rax
  PublisherConfigReader *v6; // rax
  const char *v7; // r8
  __int128 v9; // [rsp+28h] [rbp-60h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-50h] BYREF
  struct _GUID v11; // [rsp+60h] [rbp-28h] BYREF

  *(_QWORD *)&v9 = a2;
  v11 = 0;
  v9 = *(_OWORD *)(a1 + 16);
  if ( !tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(&v11, &v9) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0e5f13dae36e372ed1794705a4f26032_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v4, 31);
    throw (EvtException *)pExceptionObject;
  }
  ProcessHeap = GetProcessHeap();
  v6 = (PublisherConfigReader *)HeapAlloc(ProcessHeap, 0, 0x90u);
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_cbe02987204d3a20027a0376bdbb006d_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v7, 17);
    throw (EvtException *)pExceptionObject;
  }
  *(_QWORD *)&v9 = v6;
  *a2 = PublisherConfigReader::PublisherConfigReader(v6, &v11, *(HKEY *)a1, *(void **)(a1 + 8));
  return a2;
}

```

## disassembly

```asm
0x140004d40  mov     [rsp+arg_10], rbx
0x140004d45  push    rdi
0x140004d46  sub     rsp, 80h
0x140004d4d  mov     rax, cs:__security_cookie
0x140004d54  xor     rax, rsp
0x140004d57  mov     [rsp+88h+var_18], rax
0x140004d5c  mov     rbx, rdx
0x140004d5f  mov     rdi, rcx
0x140004d62  mov     qword ptr [rsp+88h+var_60], rdx
0x140004d67  xorps   xmm0, xmm0
0x140004d6a  movups  xmmword ptr [rsp+88h+var_28.Data1], xmm0
0x140004d6f  movups  xmm1, xmmword ptr [rcx+10h]
0x140004d73  movups  [rsp+88h+var_60], xmm1
0x140004d78  lea     rdx, [rsp+88h+var_60]
0x140004d7d  lea     rcx, [rsp+88h+var_28]
0x140004d82  call    ??$string_to_guid@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@@Z; tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(_GUID *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x140004d87  test    rax, rax
0x140004d8a  jz      short loc_140004DEA
0x140004d8c  call    cs:__imp_GetProcessHeap
0x140004d92  mov     rcx, rax; hHeap
0x140004d95  xor     edx, edx; dwFlags
0x140004d97  mov     r8d, 90h; dwBytes
0x140004d9d  call    cs:__imp_HeapAlloc
0x140004da3  test    rax, rax
0x140004da6  jz      loc_140004E48
0x140004dac  mov     qword ptr [rsp+88h+var_60], rax
0x140004db1  mov     r9, [rdi+8]; void *
0x140004db5  mov     r8, [rdi]; HKEY
0x140004db8  lea     rdx, [rsp+88h+var_28]; struct _GUID *
0x140004dbd  mov     rcx, rax; this
0x140004dc0  call    ??0PublisherConfigReader@@IEAA@AEBU_GUID@@PEAUHKEY__@@PEAX@Z; PublisherConfigReader::PublisherConfigReader(_GUID const &,HKEY__ *,void *)
0x140004dc5  nop
0x140004dc6  mov     [rbx], rax
0x140004dc9  mov     rax, rbx
0x140004dcc  mov     rcx, [rsp+88h+var_18]
0x140004dd1  xor     rcx, rsp; StackCookie
0x140004dd4  call    __security_check_cookie
0x140004dd9  mov     rbx, [rsp+88h+arg_10]
0x140004de1  add     rsp, 80h
0x140004de8  pop     rdi
0x140004de9  retn
0x140004dea  lea     rax, WPP_GLOBAL_Control
0x140004df1  mov     rcx, cs:WPP_GLOBAL_Control
0x140004df8  cmp     rcx, rax
0x140004dfb  jz      short loc_140004E21
0x140004dfd  test    byte ptr [rcx+1Ch], 4
0x140004e01  jz      short loc_140004E21
0x140004e03  cmp     byte ptr [rcx+19h], 2
0x140004e07  jb      short loc_140004E21
0x140004e09  mov     edx, 0Dh
0x140004e0e  mov     r9d, edx
0x140004e11  lea     r8, WPP_0e5f13dae36e372ed1794705a4f26032_Traceguids
0x140004e18  mov     rcx, [rcx+10h]
0x140004e1c  call    WPP_SF_d
0x140004e21  mov     edx, 0Dh; unsigned int
0x140004e26  mov     r9d, 1Fh; int
0x140004e2c  lea     rcx, [rsp+88h+pExceptionObject]; this
0x140004e31  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140004e36  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140004e3d  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x140004e42  call    _CxxThrowException_0
0x140004e48  lea     rax, WPP_GLOBAL_Control
0x140004e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e56  cmp     rcx, rax
0x140004e59  jz      short loc_140004E85
0x140004e5b  test    dword ptr [rcx+1Ch], 400000h
0x140004e62  jz      short loc_140004E85
0x140004e64  cmp     byte ptr [rcx+19h], 2
0x140004e68  jb      short loc_140004E85
0x140004e6a  mov     edx, 0Ah
0x140004e6f  mov     r9d, 0Eh
0x140004e75  lea     r8, WPP_cbe02987204d3a20027a0376bdbb006d_Traceguids
0x140004e7c  mov     rcx, [rcx+10h]
0x140004e80  call    WPP_SF_d
0x140004e85  mov     edx, 0Eh; unsigned int
0x140004e8a  mov     r9d, 11h; int
0x140004e90  lea     rcx, [rsp+88h+pExceptionObject]; this
0x140004e95  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140004e9a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140004ea1  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x140004ea6  call    _CxxThrowException_0
```
