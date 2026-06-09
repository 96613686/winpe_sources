# HrValidateContentType(_EXTENSION_CONTROL_BLOCK *)

- ea: `0x180009070`
- end: `0x1800091f8`
- name: `?HrValidateContentType@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180005e60`
- `0x180006764`

## callees

- `0x180001400`
- `0x180002504`
- `0x1800038ec`
- `0x180009070`
- `0x180009c44`
- `0x18000baa9`
- `0x18000c010`

## string_xrefs

- `0x1800090c6`: `text/xml`

## pseudocode

```c
__int64 __fastcall HrValidateContentType(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  BOOL (__stdcall *GetServerVariable)(HCONN, LPSTR, LPVOID, LPDWORD); // rax
  HCONN ConnID; // rcx
  unsigned int v3; // edi
  _QWORD *v4; // rcx
  unsigned int Win32Error; // eax
  int v7[4]; // [rsp+30h] [rbp-228h] BYREF
  char Str1[512]; // [rsp+40h] [rbp-218h] BYREF

  GetServerVariable = a1->GetServerVariable;
  ConnID = a1->ConnID;
  v7[0] = 512;
  if ( !((unsigned int (__fastcall *)(HCONN, const char *, char *, int *))GetServerVariable)(
          ConnID,
          "CONTENT_TYPE",
          Str1,
          v7) )
  {
    Win32Error = HrFromLastWin32Error();
    v3 = Win32Error;
    if ( !Win32Error )
      return v3;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrValidateContentType(): Failed to get content type",
      Win32Error);
    goto LABEL_13;
  }
  if ( !strncmp_0(Str1, "text/xml", 8u) )
  {
    v3 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids, Str1);
    return v3;
  }
  v3 = -2147180032;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v3;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids, Str1);
LABEL_13:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_14:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
    WPP_SF_sd(
      v4[2],
      58,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrValidateContentType(): Exiting",
      v3);
  return v3;
}

```

## disassembly

```asm
0x180009070  mov     [rsp+arg_8], rbx
0x180009075  push    rdi
0x180009076  sub     rsp, 250h
0x18000907d  mov     rax, cs:__security_cookie
0x180009084  xor     rax, rsp
0x180009087  mov     [rsp+258h+var_18], rax
0x18000908f  mov     rax, [rcx+0A0h]
0x180009096  lea     r9, [rsp+258h+var_228]
0x18000909b  mov     rcx, [rcx+8]
0x18000909f  lea     r8, [rsp+258h+Str1]
0x1800090a4  lea     rdx, aContentType; "CONTENT_TYPE"
0x1800090ab  mov     [rsp+258h+var_228], 200h
0x1800090b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090b8  test    eax, eax
0x1800090ba  jz      loc_18000915F
0x1800090c0  mov     r8d, 8; MaxCount
0x1800090c6  lea     rdx, Str2; "text/xml"
0x1800090cd  lea     rcx, [rsp+258h+Str1]; Str1
0x1800090d2  call    strncmp_0
0x1800090d7  test    eax, eax
0x1800090d9  jnz     short loc_18000911E
0x1800090db  xor     edi, edi
0x1800090dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090e4  lea     rbx, WPP_GLOBAL_Control
0x1800090eb  cmp     rcx, rbx
0x1800090ee  jz      loc_1800091D5
0x1800090f4  test    dword ptr [rcx+1Ch], 400h
0x1800090fb  jz      loc_1800091D5
0x180009101  mov     rcx, [rcx+10h]
0x180009105  lea     edx, [rax+37h]
0x180009108  lea     r9, [rsp+258h+Str1]
0x18000910d  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180009114  call    WPP_SF_s
0x180009119  jmp     loc_1800091D5
0x18000911e  mov     edi, 8004A200h
0x180009123  mov     rcx, cs:WPP_GLOBAL_Control
0x18000912a  lea     rbx, WPP_GLOBAL_Control
0x180009131  cmp     rcx, rbx
0x180009134  jz      loc_1800091D5
0x18000913a  test    dword ptr [rcx+1Ch], 400h
0x180009141  jz      short loc_1800091AA
0x180009143  mov     rcx, [rcx+10h]
0x180009147  lea     r9, [rsp+258h+Str1]
0x18000914c  mov     edx, 38h ; '8'
0x180009151  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180009158  call    WPP_SF_s
0x18000915d  jmp     short loc_1800091A3
0x18000915f  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180009164  mov     edi, eax
0x180009166  test    eax, eax
0x180009168  jz      short loc_1800091D5
0x18000916a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009171  lea     rbx, WPP_GLOBAL_Control
0x180009178  cmp     rcx, rbx
0x18000917b  jz      short loc_1800091D5
0x18000917d  test    byte ptr [rcx+1Ch], 1
0x180009181  jz      short loc_1800091AA
0x180009183  mov     rcx, [rcx+10h]
0x180009187  lea     r9, aHrvalidatecont_0; "HrValidateContentType(): Failed to get "...
0x18000918e  mov     edx, 39h ; '9'
0x180009193  mov     [rsp+258h+var_238], eax
0x180009197  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x18000919e  call    WPP_SF_sd
0x1800091a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091aa  cmp     rcx, rbx
0x1800091ad  jz      short loc_1800091D5
0x1800091af  test    byte ptr [rcx+1Ch], 1
0x1800091b3  jz      short loc_1800091D5
0x1800091b5  mov     rcx, [rcx+10h]
0x1800091b9  lea     r9, aHrvalidatecont_1; "HrValidateContentType(): Exiting"
0x1800091c0  mov     edx, 3Ah ; ':'
0x1800091c5  mov     [rsp+258h+var_238], edi
0x1800091c9  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x1800091d0  call    WPP_SF_sd
0x1800091d5  mov     eax, edi
0x1800091d7  mov     rcx, [rsp+258h+var_18]
0x1800091df  xor     rcx, rsp; StackCookie
0x1800091e2  call    __security_check_cookie
0x1800091e7  mov     rbx, [rsp+258h+arg_8]
0x1800091ef  add     rsp, 250h
0x1800091f6  pop     rdi
0x1800091f7  retn
```
