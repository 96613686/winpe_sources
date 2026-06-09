# OnChannelNotification

- ea: `0x180005a50`
- end: `0x180005b06`
- name: `OnChannelNotification`
- size: `182`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004054`
- `0x18000526c`
- `0x180005a50`
- `0x180006d50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180005ae2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180005ae2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a70`

## pseudocode

```c
__int64 __fastcall OnChannelNotification(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rbx
  int v5; // eax
  unsigned int v6; // r8d
  int v8; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a3 )
  {
    v4 = a2 + 616;
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 616));
    v9 = v4;
    *(_DWORD *)(a2 + 668) = 1;
    if ( (*(_BYTE *)(a2 + 608) & 1) != 0 && *(_BYTE *)(a2 + 665) && !*(_BYTE *)(a2 + 666) && !*(_BYTE *)(a2 + 664) )
    {
      LOBYTE(v8) = 0;
      v5 = IsChannelOffered((struct ClientChannelParameters *)(a2 + 16), (bool *)&v8);
      if ( v5 >= 0 )
      {
        if ( (_BYTE)v8 )
        {
          SubmitThreadpoolWork(*(PTP_WORK *)(a2 + 672));
          *(_BYTE *)(a2 + 666) = 1;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x405, v6, (const char *)(unsigned int)v5, v8);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180005a50  mov     [rsp+arg_0], rbx
0x180005a55  push    rdi
0x180005a56  sub     rsp, 30h
0x180005a5a  mov     rdi, rdx
0x180005a5d  test    r8d, r8d
0x180005a60  jnz     loc_180005AF9
0x180005a66  lea     rbx, [rdx+268h]
0x180005a6d  mov     rcx, rbx; lpCriticalSection
0x180005a70  call    cs:__imp_EnterCriticalSection
0x180005a76  mov     [rsp+38h+var_10], rbx
0x180005a7b  mov     dword ptr [rdi+29Ch], 1
0x180005a85  test    byte ptr [rdi+260h], 1
0x180005a8c  jz      short loc_180005AEF
0x180005a8e  cmp     byte ptr [rdi+299h], 0
0x180005a95  jz      short loc_180005AEF
0x180005a97  cmp     byte ptr [rdi+29Ah], 0
0x180005a9e  jnz     short loc_180005AEF
0x180005aa0  cmp     byte ptr [rdi+298h], 0
0x180005aa7  jnz     short loc_180005AEF
0x180005aa9  mov     byte ptr [rsp+38h+var_18], 0; int
0x180005aae  lea     rcx, [rdi+10h]; struct ClientChannelParameters *
0x180005ab2  lea     rdx, [rsp+38h+var_18]; bool *
0x180005ab7  call    ?IsChannelOffered@@YAJPEAUClientChannelParameters@@PEA_N@Z; IsChannelOffered(ClientChannelParameters *,bool *)
0x180005abc  mov     rcx, [rsp+38h]; this
0x180005ac1  test    eax, eax
0x180005ac3  jns     short loc_180005AD4
0x180005ac5  mov     r9d, eax; char *
0x180005ac8  mov     edx, 405h; void *
0x180005acd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005ad2  jmp     short loc_180005AEF
0x180005ad4  cmp     byte ptr [rsp+38h+var_18], 0
0x180005ad9  jz      short loc_180005AEF
0x180005adb  mov     rcx, [rdi+2A0h]; pwk
0x180005ae2  call    cs:__imp_SubmitThreadpoolWork
0x180005ae8  mov     byte ptr [rdi+29Ah], 1
0x180005aef  lea     rcx, [rsp+38h+var_10]
0x180005af4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180005af9  xor     eax, eax
0x180005afb  mov     rbx, [rsp+38h+arg_0]
0x180005b00  add     rsp, 30h
0x180005b04  pop     rdi
0x180005b05  retn
```
