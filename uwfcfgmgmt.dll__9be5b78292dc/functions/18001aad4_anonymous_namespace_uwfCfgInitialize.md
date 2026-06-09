# _anonymous_namespace_::uwfCfgInitialize

- ea: `0x18001aad4`
- end: `0x18001abf4`
- name: `_anonymous_namespace_::uwfCfgInitialize`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `31`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180017d50`
- `0x180017df0`
- `0x180017e90`
- `0x180017fa0`
- `0x180018080`
- `0x1800182e0`
- `0x180018390`
- `0x180018430`
- `0x180018540`
- `0x1800185f0`
- `0x180018720`
- `0x180018950`
- `0x180018cf0`
- `0x180018d90`
- `0x180018e40`
- `0x180019070`
- `0x1800191a0`
- `0x180019260`
- `0x180019310`
- `0x1800193c0`
- `0x180019690`
- `0x180019730`
- `0x1800197d0`
- `0x180019a30`
- `0x180019e70`
- `0x18001a080`
- `0x18001a110`
- `0x18001a2d0`
- `0x18001a4e0`
- `0x18001a580`
- `0x18001a620`

## callees

- `0x18000ee48`
- `0x180011130`
- `0x180017b90`
- `0x180017c20`
- `0x18001aad4`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab54`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::uwfCfgInitialize(
        bool a1,
        char a2,
        CUwfProvider **a3,
        struct CUwfStaticConfiguration **a4,
        unsigned __int16 *a5,
        struct CUwfStaticVolumeConfiguration **a6)
{
  int StaticConfiguration; // ecx
  unsigned int v11; // edx
  int Config; // eax
  unsigned __int16 v14[48]; // [rsp+20h] [rbp-98h] BYREF

  memset_0(v14, 0, 0x5Au);
  if ( a3 && a4 && (!a5 || a6) )
  {
    *a3 = (CUwfProvider *)&CUwfProvider::s_UwfProvider;
    EnterCriticalSection(&CUwfProvider::s_CritSec);
    StaticConfiguration = CUwfProvider::Begin(*a3, a1);
    if ( StaticConfiguration >= 0 )
    {
      StaticConfiguration = CUwfProvider::GetStaticConfiguration(*a3, a2, a4);
      if ( StaticConfiguration >= 0 )
      {
        if ( *a4 )
        {
          if ( a5 )
          {
            StaticConfiguration = ConstructVolumeNameFromVolumeIdentifier(v14, v11, a5);
            if ( StaticConfiguration >= 0 )
            {
              Config = VolumeGetConfig(*a4, v14, 0, a6);
              StaticConfiguration = Config;
              if ( Config >= 0 )
              {
                if ( !*a6 )
                  return (unsigned int)-2147467259;
                return (unsigned int)Config;
              }
            }
          }
        }
        else
        {
          return (unsigned int)-2147467259;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)StaticConfiguration;
}

```

## disassembly

```asm
0x18001aad4  mov     [rsp+arg_0], rbx
0x18001aad9  push    rbp
0x18001aada  push    rsi
0x18001aadb  push    rdi
0x18001aadc  push    r14
0x18001aade  push    r15
0x18001aae0  sub     rsp, 90h
0x18001aae7  mov     rax, cs:__security_cookie
0x18001aaee  xor     rax, rsp
0x18001aaf1  mov     [rsp+0B8h+var_38], rax
0x18001aaf9  mov     rdi, [rsp+0B8h+arg_20]
0x18001ab01  mov     bpl, dl
0x18001ab04  mov     rsi, [rsp+0B8h+arg_28]
0x18001ab0c  xor     edx, edx; Val
0x18001ab0e  mov     r14, r8
0x18001ab11  mov     r15b, cl
0x18001ab14  lea     rcx, [rsp+0B8h+var_98]; void *
0x18001ab19  mov     rbx, r9
0x18001ab1c  lea     r8d, [rdx+5Ah]; Size
0x18001ab20  call    memset_0
0x18001ab25  test    r14, r14
0x18001ab28  jnz     short loc_18001AB34
0x18001ab2a  mov     ecx, 80070057h
0x18001ab2f  jmp     loc_18001ABCB
0x18001ab34  test    rbx, rbx
0x18001ab37  jz      short loc_18001AB2A
0x18001ab39  test    rdi, rdi
0x18001ab3c  jz      short loc_18001AB43
0x18001ab3e  test    rsi, rsi
0x18001ab41  jz      short loc_18001AB2A
0x18001ab43  lea     rax, ?s_UwfProvider@CUwfProvider@@0V1@A; CUwfProvider CUwfProvider::s_UwfProvider
0x18001ab4a  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ab51  mov     [r14], rax
0x18001ab54  call    cs:__imp_EnterCriticalSection
0x18001ab5a  mov     rcx, [r14]; this
0x18001ab5d  mov     dl, r15b; bool
0x18001ab60  call    ?Begin@CUwfProvider@@QEAAJ_N@Z; CUwfProvider::Begin(bool)
0x18001ab65  mov     ecx, eax
0x18001ab67  test    eax, eax
0x18001ab69  js      short loc_18001ABCB
0x18001ab6b  mov     rcx, [r14]; this
0x18001ab6e  mov     r8, rbx; struct CUwfStaticConfiguration **
0x18001ab71  mov     dl, bpl; bool
0x18001ab74  call    ?GetStaticConfiguration@CUwfProvider@@QEAAJ_NPEAPEAVCUwfStaticConfiguration@@@Z; CUwfProvider::GetStaticConfiguration(bool,CUwfStaticConfiguration * *)
0x18001ab79  mov     ecx, eax
0x18001ab7b  test    eax, eax
0x18001ab7d  js      short loc_18001ABCB
0x18001ab7f  cmp     qword ptr [rbx], 0
0x18001ab83  jnz     short loc_18001AB8C
0x18001ab85  mov     ecx, 80004005h
0x18001ab8a  jmp     short loc_18001ABCB
0x18001ab8c  test    rdi, rdi
0x18001ab8f  jz      short loc_18001ABCB
0x18001ab91  mov     r8, rdi; unsigned __int16 *
0x18001ab94  lea     rcx, [rsp+0B8h+var_98]; unsigned __int16 *
0x18001ab99  call    ?ConstructVolumeNameFromVolumeIdentifier@@YAJPEAGKPEBG@Z; ConstructVolumeNameFromVolumeIdentifier(ushort *,ulong,ushort const *)
0x18001ab9e  mov     ecx, eax
0x18001aba0  test    eax, eax
0x18001aba2  js      short loc_18001ABCB
0x18001aba4  mov     rcx, [rbx]; this
0x18001aba7  lea     rdx, [rsp+0B8h+var_98]; unsigned __int16 *
0x18001abac  mov     r9, rsi; struct CUwfStaticVolumeConfiguration **
0x18001abaf  xor     r8d, r8d; unsigned __int16 *
0x18001abb2  call    ?VolumeGetConfig@@YAJPEAVCUwfStaticConfiguration@@PEBG1PEAPEAVCUwfStaticVolumeConfiguration@@@Z; VolumeGetConfig(CUwfStaticConfiguration *,ushort const *,ushort const *,CUwfStaticVolumeConfiguration * *)
0x18001abb7  mov     ecx, eax
0x18001abb9  test    eax, eax
0x18001abbb  js      short loc_18001ABCB
0x18001abbd  cmp     qword ptr [rsi], 0
0x18001abc1  mov     ecx, 80004005h
0x18001abc6  cmovz   eax, ecx
0x18001abc9  mov     ecx, eax
0x18001abcb  mov     eax, ecx
0x18001abcd  mov     rcx, [rsp+0B8h+var_38]
0x18001abd5  xor     rcx, rsp; StackCookie
0x18001abd8  call    __security_check_cookie
0x18001abdd  mov     rbx, [rsp+0B8h+arg_0]
0x18001abe5  add     rsp, 90h
0x18001abec  pop     r15
0x18001abee  pop     r14
0x18001abf0  pop     rdi
0x18001abf1  pop     rsi
0x18001abf2  pop     rbp
0x18001abf3  retn
```
