# ChannelConfigWriter::GetChannelConfigReader(void)

- ea: `0x140005f20`
- end: `0x140005fff`
- name: `?GetChannelConfigReader@ChannelConfigWriter@@QEAA?AV?$unique_ptr@VChannelConfigReader@@U?$default_delete@VChannelConfigReader@@@utl@@@utl@@XZ`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400178bc`

## callees

- `0x140005f20`
- `0x140006008`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005f30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005f30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005f41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005f41`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall ChannelConfigWriter::GetChannelConfigReader(__int64 *a1, __int64 *a2)
{
  HANDLE ProcessHeap; // rax
  LPVOID v5; // rax
  const char *v6; // r8
  __int128 v8; // [rsp+30h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+40h] [rbp-38h] BYREF

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, 0x90u);
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_cbe02987204d3a20027a0376bdbb006d_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v6, 17);
    throw (EvtException *)pExceptionObject;
  }
  *(_QWORD *)&v8 = a1[35];
  *((_QWORD *)&v8 + 1) = (a1[36] - (__int64)v8) >> 1;
  *a2 = ChannelConfigReader::ChannelConfigReader((__int64)v5, &v8, a1[34]);
  return a2;
}

```

## disassembly

```asm
0x140005f20  mov     [rsp+arg_0], rbx
0x140005f25  push    rdi
0x140005f26  sub     rsp, 70h
0x140005f2a  mov     rbx, rdx
0x140005f2d  mov     rdi, rcx
0x140005f30  call    cs:__imp_GetProcessHeap
0x140005f36  mov     rcx, rax; hHeap
0x140005f39  xor     edx, edx; dwFlags
0x140005f3b  mov     r8d, 90h; dwBytes
0x140005f41  call    cs:__imp_HeapAlloc
0x140005f47  test    rax, rax
0x140005f4a  jnz     short loc_140005FB0
0x140005f4c  lea     rax, WPP_GLOBAL_Control
0x140005f53  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f5a  cmp     rcx, rax
0x140005f5d  jz      short loc_140005F89
0x140005f5f  test    dword ptr [rcx+1Ch], 400000h
0x140005f66  jz      short loc_140005F89
0x140005f68  cmp     byte ptr [rcx+19h], 2
0x140005f6c  jb      short loc_140005F89
0x140005f6e  mov     edx, 0Ah
0x140005f73  mov     r9d, 0Eh
0x140005f79  lea     r8, WPP_cbe02987204d3a20027a0376bdbb006d_Traceguids
0x140005f80  mov     rcx, [rcx+10h]
0x140005f84  call    WPP_SF_d
0x140005f89  mov     edx, 0Eh; unsigned int
0x140005f8e  mov     r9d, 11h; int
0x140005f94  lea     rcx, [rsp+78h+pExceptionObject]; this
0x140005f99  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140005f9e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140005fa5  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x140005faa  call    _CxxThrowException_0
0x140005fb0  mov     [rsp+78h+arg_10], rax
0x140005fb8  mov     rcx, [rdi+118h]
0x140005fbf  mov     [rsp+78h+var_48], rcx
0x140005fc4  mov     rdx, [rdi+120h]
0x140005fcb  sub     rdx, rcx
0x140005fce  sar     rdx, 1
0x140005fd1  mov     [rsp+78h+var_40], rdx
0x140005fd6  mov     r8, [rdi+110h]
0x140005fdd  lea     rdx, [rsp+78h+var_48]
0x140005fe2  mov     rcx, rax
0x140005fe5  call    ??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x140005fea  nop
0x140005feb  mov     [rbx], rax
0x140005fee  mov     rax, rbx
0x140005ff1  mov     rbx, [rsp+78h+arg_0]
0x140005ff9  add     rsp, 70h
0x140005ffd  pop     rdi
0x140005ffe  retn
```
