# CUserSetting::DeserializeField(ushort const *,uint,WDS_DATA *,int)

- ea: `0x180004eb0`
- end: `0x180004fd7`
- name: `?DeserializeField@CUserSetting@@IEAAJPEBGIPEAUWDS_DATA@@H@Z`
- size: `295`
- prototype: `__int64 __usercall@<rax>(CUserSetting *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, struct WDS_DATA *@<r9>, int)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180004fe0`
- `0x180005140`
- `0x180005190`
- `0x180005400`
- `0x180005480`

## callees

- `0x180004df0`
- `0x180004eb0`
- `0x1800051e0`
- `0x180005260`
- `0x1800054d0`
- `0x18000892c`
- `0x1800319ae`
- `0x1800319f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004f73`
- `KERNEL32!GetLastError` at `0x180004f73`
- `WDSCORE!CurrentIP` at `0x180004f0e`
- `WDSCORE!CurrentIP` at `0x180004f0e`
- `WDSCORE!WdsFreeData` at `0x180004f99`
- `WDSCORE!WdsFreeData` at `0x180004f99`
- `WDSCORE!WdsGetBlackboardValue` at `0x180004f5b`
- `WDSCORE!WdsGetBlackboardValue` at `0x180004f5b`

## string_xrefs

- `0x180004f2c`: `CUserSetting::DeserializeField`

## pseudocode

```c
signed int __fastcall CUserSetting::DeserializeField(
        CUserSetting *this,
        const unsigned __int16 *a2,
        int a3,
        struct WDS_DATA *a4,
        int a5)
{
  void *v9; // rax
  unsigned int v10; // ecx
  const unsigned __int16 *v11; // r9
  struct _BLACKBOARD *Blackboard; // rax
  signed int result; // eax
  unsigned __int16 v14[264]; // [rsp+30h] [rbp-238h] BYREF

  memset_0(v14, 0, 0x208u);
  if ( CUserSetting::GetKeyName(this, v14, 260, a5) < 0 )
  {
    v9 = (void *)CurrentIP();
    Ui_Assert(v10, "(((HRESULT)(hRes)) >= 0)", 0x13Fu, v11, L"CUserSetting::DeserializeField", v9);
  }
  CUserSetting::AcquireMutex(this);
  Blackboard = CUserSetting::GetBlackboard(this);
  if ( (unsigned int)WdsGetBlackboardValue(Blackboard, v14, a2, a4) )
  {
    if ( *(_DWORD *)a4 == a3 )
    {
      CUserSetting::ReleaseMutex(this);
      return 0;
    }
    else
    {
      CUserSetting::ReleaseMutex(this);
      WdsFreeData(a4);
      return -2147352571;
    }
  }
  else
  {
    CUserSetting::ReleaseMutex(this);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180004eb0  mov     [rsp+arg_10], rbx
0x180004eb5  push    rbp
0x180004eb6  push    rsi
0x180004eb7  push    rdi
0x180004eb8  sub     rsp, 250h
0x180004ebf  mov     rax, cs:__security_cookie
0x180004ec6  xor     rax, rsp
0x180004ec9  mov     [rsp+268h+var_28], rax
0x180004ed1  mov     esi, r8d
0x180004ed4  mov     rbp, rdx
0x180004ed7  mov     rbx, rcx
0x180004eda  xor     edx, edx; Val
0x180004edc  mov     r8d, 208h; Size
0x180004ee2  lea     rcx, [rsp+268h+var_238]; void *
0x180004ee7  mov     rdi, r9
0x180004eea  call    memset_0
0x180004eef  mov     r9d, [rsp+268h+arg_20]; int
0x180004ef7  lea     rdx, [rsp+268h+var_238]; unsigned __int16 *
0x180004efc  mov     r8d, 104h; int
0x180004f02  mov     rcx, rbx; this
0x180004f05  call    ?GetKeyName@CUserSetting@@IEAAJPEAGHH@Z; CUserSetting::GetKeyName(ushort *,int,int)
0x180004f0a  test    eax, eax
0x180004f0c  jns     short loc_180004F3D
0x180004f0e  call    cs:__imp_CurrentIP
0x180004f15  nop     dword ptr [rax+rax+00h]
0x180004f1a  mov     [rsp+268h+var_240], rax; void *
0x180004f1f  mov     r8d, 13Fh; unsigned int
0x180004f25  lea     rdx, aHresultHres0; "(((HRESULT)(hRes)) >= 0)"
0x180004f2c  lea     rax, aCusersettingDe; "CUserSetting::DeserializeField"
0x180004f33  mov     [rsp+268h+var_248], rax; unsigned __int16 *
0x180004f38  call    ?Ui_Assert@@YAXKPEBDKPEBG1PEAX@Z; Ui_Assert(ulong,char const *,ulong,ushort const *,ushort const *,void *)
0x180004f3d  mov     rcx, rbx; this
0x180004f40  call    ?AcquireMutex@CUserSetting@@IEAAXXZ; CUserSetting::AcquireMutex(void)
0x180004f45  mov     rcx, rbx; this
0x180004f48  call    ?GetBlackboard@CUserSetting@@IEAAPEAU_BLACKBOARD@@XZ; CUserSetting::GetBlackboard(void)
0x180004f4d  mov     rcx, rax
0x180004f50  lea     rdx, [rsp+268h+var_238]
0x180004f55  mov     r9, rdi
0x180004f58  mov     r8, rbp
0x180004f5b  call    cs:__imp_WdsGetBlackboardValue
0x180004f62  nop     dword ptr [rax+rax+00h]
0x180004f67  mov     rcx, rbx; this
0x180004f6a  test    eax, eax
0x180004f6c  jnz     short loc_180004F8D
0x180004f6e  call    ?ReleaseMutex@CUserSetting@@IEAAXXZ; CUserSetting::ReleaseMutex(void)
0x180004f73  call    cs:__imp_GetLastError
0x180004f7a  nop     dword ptr [rax+rax+00h]
0x180004f7f  test    eax, eax
0x180004f81  jle     short loc_180004FB3
0x180004f83  movzx   eax, ax
0x180004f86  or      eax, 80070000h
0x180004f8b  jmp     short loc_180004FB3
0x180004f8d  cmp     [rdi], esi
0x180004f8f  jz      short loc_180004FAC
0x180004f91  call    ?ReleaseMutex@CUserSetting@@IEAAXXZ; CUserSetting::ReleaseMutex(void)
0x180004f96  mov     rcx, rdi
0x180004f99  call    cs:__imp_WdsFreeData
0x180004fa0  nop     dword ptr [rax+rax+00h]
0x180004fa5  mov     eax, 80020005h
0x180004faa  jmp     short loc_180004FB3
0x180004fac  call    ?ReleaseMutex@CUserSetting@@IEAAXXZ; CUserSetting::ReleaseMutex(void)
0x180004fb1  xor     eax, eax
0x180004fb3  mov     rcx, [rsp+268h+var_28]
0x180004fbb  xor     rcx, rsp; StackCookie
0x180004fbe  call    __security_check_cookie
0x180004fc3  mov     rbx, [rsp+268h+arg_10]
0x180004fcb  add     rsp, 250h
0x180004fd2  pop     rdi
0x180004fd3  pop     rsi
0x180004fd4  pop     rbp
0x180004fd5  retn
```
