# CAutoImpersonate::~CAutoImpersonate(void)

- ea: `0x180007d20`
- end: `0x180007dd2`
- name: `??1CAutoImpersonate@@QEAA@XZ`
- size: `178`
- prototype: `void __fastcall(CAutoImpersonate *__hidden this)`
- caller_count: `40`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000917c`
- `0x180009244`
- `0x18000a360`
- `0x18000a3c0`
- `0x18000a7a0`
- `0x18000aa40`
- `0x18000ae20`
- `0x18000ae80`
- `0x18000aee0`
- `0x18000af40`
- `0x18000afa0`
- `0x18000b000`
- `0x18000b050`
- `0x18000b570`
- `0x18000b730`
- `0x18000bd90`
- `0x18000c180`
- `0x180011120`
- `0x180011180`
- `0x1800111d0`
- `0x180011240`
- `0x180011310`
- `0x1800113e0`
- `0x180011440`
- `0x1800114a0`
- `0x180011500`
- `0x180011560`
- `0x1800115c0`
- `0x180011620`
- `0x1800116e0`
- `0x180011740`
- `0x1800117a0`
- `0x180011860`
- `0x180011920`
- `0x180011980`
- `0x1800119e0`
- `0x180011a40`
- `0x180011aa0`
- `0x180011b60`
- `0x180011bc0`

## callees

- `0x180006c9c`
- `0x180007d20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007d76`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007d76`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180007d33`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180007d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d80`

## pseudocode

```c
void __fastcall CAutoImpersonate::~CAutoImpersonate(CAutoImpersonate *this)
{
  HRESULT v1; // eax
  signed int LastError; // eax

  if ( *(_DWORD *)this )
  {
    if ( *(_DWORD *)this == 1 )
    {
      v1 = CoRevertToSelf();
      if ( v1 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids,
          (unsigned int)v1);
      }
    }
  }
  else if ( !RevertToSelf() )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids,
        (unsigned int)LastError);
  }
}

```

## disassembly

```asm
0x180007d20  sub     rsp, 28h
0x180007d24  mov     edx, [rcx]
0x180007d26  test    edx, edx
0x180007d28  jz      short loc_180007D76
0x180007d2a  cmp     edx, 1
0x180007d2d  jnz     loc_180007DCD
0x180007d33  call    cs:__imp_CoRevertToSelf
0x180007d39  test    eax, eax
0x180007d3b  jns     loc_180007DCD
0x180007d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d48  lea     rdx, WPP_GLOBAL_Control
0x180007d4f  cmp     rcx, rdx
0x180007d52  jz      short loc_180007DCD
0x180007d54  test    byte ptr [rcx+1Ch], 1
0x180007d58  jz      short loc_180007DCD
0x180007d5a  mov     rcx, [rcx+10h]
0x180007d5e  lea     r8, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids
0x180007d65  mov     edx, 10h
0x180007d6a  mov     r9d, eax
0x180007d6d  add     rsp, 28h
0x180007d71  jmp     WPP_SF_d
0x180007d76  call    cs:__imp_RevertToSelf
0x180007d7c  test    eax, eax
0x180007d7e  jnz     short loc_180007DCD
0x180007d80  call    cs:__imp_GetLastError
0x180007d86  test    eax, eax
0x180007d88  jle     short loc_180007D92
0x180007d8a  movzx   eax, ax
0x180007d8d  or      eax, 80070000h
0x180007d92  test    eax, eax
0x180007d94  mov     ecx, 80004005h
0x180007d99  cmovns  eax, ecx
0x180007d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007da3  lea     rdx, WPP_GLOBAL_Control
0x180007daa  cmp     rcx, rdx
0x180007dad  jz      short loc_180007DCD
0x180007daf  test    byte ptr [rcx+1Ch], 1
0x180007db3  jz      short loc_180007DCD
0x180007db5  mov     rcx, [rcx+10h]
0x180007db9  lea     r8, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids
0x180007dc0  mov     edx, 0Fh
0x180007dc5  mov     r9d, eax
0x180007dc8  call    WPP_SF_d
0x180007dcd  add     rsp, 28h
0x180007dd1  retn
```
