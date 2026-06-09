# TestHookPolicyReader::IsValidAUTestCabContent(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18001901c`
- end: `0x1800191ce`
- name: `?IsValidAUTestCabContent@TestHookPolicyReader@@CA_NAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `434`
- prototype: `char __fastcall(char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180018bc4`

## callees

- `0x18001901c`
- `0x18001a1b0`
- `0x18001a24c`
- `0x180027f98`
- `0x18002ffd0`
- `0x1800371b0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180019125`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180019125`

## string_xrefs

- `0x180019057`: `Windows Update Test Key Authorization File\n`

## pseudocode

```c
char __fastcall TestHookPolicyReader::IsValidAUTestCabContent(char **a1)
{
  char *v2; // rsi
  size_t v3; // rbx
  size_t v4; // rdi
  void **v6; // rdx
  __int64 v7; // [rsp+20h] [rbp-68h] BYREF
  __int64 v8; // [rsp+28h] [rbp-60h] BYREF
  char v9; // [rsp+30h] [rbp-58h]
  void *Buf2[2]; // [rsp+38h] [rbp-50h] BYREF
  size_t Size[2]; // [rsp+48h] [rbp-40h]
  _OWORD v12[2]; // [rsp+58h] [rbp-30h] BYREF

  *(_OWORD *)Buf2 = 0;
  *(_OWORD *)Size = 0;
  std::string::_Construct<1,char const *>(Buf2, "Windows Update Test Key Authorization File\r\n", 44);
  v2 = *a1;
  v3 = a1[1] - *a1;
  v4 = Size[0];
  if ( v3 < Size[0] )
    goto LABEL_2;
  v6 = Buf2;
  if ( Size[1] > 0xF )
    v6 = (void **)Buf2[0];
  if ( !memcmp(v2, v6, Size[0]) )
  {
    memset(v12, 0, sizeof(v12));
    std::string::_Construct<1,char const *>(v12, &v2[v4], v3 - v4);
    PolicyUtils::Time::ConvertStringToTime(&v8, v12);
    if ( v9 )
    {
      v7 = 0;
      GetSystemTimePreciseAsFileTime(&v7);
      if ( (unsigned int)((__int64)((unsigned int)v7 + ((unsigned __int64)HIDWORD(v7) << 32) - v8 - 116444736000000000LL)
                        / 10000000) > 0x127500 )
      {
        std::string::~string(v12);
        std::string::~string(Buf2);
        return 0;
      }
      else
      {
        std::string::~string(v12);
        std::string::~string(Buf2);
        return 1;
      }
    }
    else
    {
      std::string::~string(v12);
      std::string::~string(Buf2);
      return 0;
    }
  }
  else
  {
LABEL_2:
    std::string::~string(Buf2);
    return 0;
  }
}

```

## disassembly

```asm
0x18001901c  mov     [rsp+arg_8], rbx
0x180019021  mov     [rsp+arg_10], rsi
0x180019026  push    rdi
0x180019027  sub     rsp, 80h
0x18001902e  mov     rax, cs:__security_cookie
0x180019035  xor     rax, rsp
0x180019038  mov     [rsp+88h+var_10], rax
0x18001903d  mov     rbx, rcx
0x180019040  xorps   xmm0, xmm0
0x180019043  movups  xmmword ptr [rsp+88h+Buf2], xmm0
0x180019048  xorps   xmm1, xmm1
0x18001904b  movdqu  xmmword ptr [rsp+88h+Size], xmm1
0x180019051  mov     r8d, 2Ch ; ','
0x180019057  lea     rdx, aWindowsUpdateT; "Windows Update Test Key Authorization F"...
0x18001905e  lea     rcx, [rsp+88h+Buf2]
0x180019063  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180019068  nop
0x180019069  mov     rsi, [rbx]
0x18001906c  mov     rbx, [rbx+8]
0x180019070  sub     rbx, rsi
0x180019073  mov     rdi, [rsp+88h+Size]
0x180019078  cmp     rbx, rdi
0x18001907b  jnb     short loc_18001908E
0x18001907d  lea     rcx, [rsp+88h+Buf2]
0x180019082  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180019087  xor     al, al
0x180019089  jmp     loc_1800191AB
0x18001908e  lea     rdx, [rsp+88h+Buf2]
0x180019093  cmp     [rsp+88h+Size+8], 0Fh
0x180019099  cmova   rdx, [rsp+88h+Buf2]; Buf2
0x18001909f  mov     r8, rdi; Size
0x1800190a2  mov     rcx, rsi; Buf1
0x1800190a5  call    memcmp
0x1800190aa  test    eax, eax
0x1800190ac  jz      short loc_1800190BF
0x1800190ae  lea     rcx, [rsp+88h+Buf2]
0x1800190b3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800190b8  xor     al, al
0x1800190ba  jmp     loc_1800191AB
0x1800190bf  xorps   xmm0, xmm0
0x1800190c2  movups  [rsp+88h+var_30], xmm0
0x1800190c7  xorps   xmm1, xmm1
0x1800190ca  movdqu  [rsp+88h+var_20], xmm1
0x1800190d0  sub     rbx, rdi
0x1800190d3  lea     rdx, [rsi+rdi]
0x1800190d7  mov     r8, rbx
0x1800190da  lea     rcx, [rsp+88h+var_30]
0x1800190df  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800190e4  nop
0x1800190e5  lea     rdx, [rsp+88h+var_30]
0x1800190ea  lea     rcx, [rsp+88h+var_60]
0x1800190ef  call    ?ConvertStringToTime@Time@PolicyUtils@@YA?AV?$optional@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; PolicyUtils::Time::ConvertStringToTime(std::string const &)
0x1800190f4  cmp     [rsp+88h+var_58], 0
0x1800190f9  jnz     short loc_180019117
0x1800190fb  lea     rcx, [rsp+88h+var_30]
0x180019100  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180019105  nop
0x180019106  lea     rcx, [rsp+88h+Buf2]
0x18001910b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180019110  xor     al, al
0x180019112  jmp     loc_1800191AB
0x180019117  mov     [rsp+88h+var_68], 0
0x180019120  lea     rcx, [rsp+88h+var_68]
0x180019125  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18001912b  mov     r8d, dword ptr [rsp+88h+var_68+4]
0x180019130  shl     r8, 20h
0x180019134  sub     r8, [rsp+88h+var_60]
0x180019139  mov     ecx, dword ptr [rsp+88h+var_68]
0x18001913d  mov     rdx, 0FE624E212AC18000h
0x180019147  add     r8, rdx
0x18001914a  add     r8, rcx
0x18001914d  mov     rax, 0D6BF94D5E57A42BDh
0x180019157  imul    r8
0x18001915a  add     rdx, r8
0x18001915d  sar     rdx, 17h
0x180019161  mov     rax, rdx
0x180019164  shr     rax, 3Fh
0x180019168  add     rdx, rax
0x18001916b  test    edx, edx
0x18001916d  js      short loc_180019190
0x18001916f  cmp     edx, 127500h
0x180019175  ja      short loc_180019190
0x180019177  lea     rcx, [rsp+88h+var_30]
0x18001917c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180019181  nop
0x180019182  lea     rcx, [rsp+88h+Buf2]
0x180019187  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001918c  mov     al, 1
0x18001918e  jmp     short loc_1800191AB
0x180019190  lea     rcx, [rsp+88h+var_30]
0x180019195  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001919a  nop
0x18001919b  lea     rcx, [rsp+88h+Buf2]
0x1800191a0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800191a5  xor     al, al
0x1800191a7  jmp     short loc_1800191AB
0x1800191a9  xor     al, al
0x1800191ab  mov     rcx, [rsp+88h+var_10]
0x1800191b0  xor     rcx, rsp; StackCookie
0x1800191b3  call    __security_check_cookie
0x1800191b8  lea     r11, [rsp+88h+var_8]
0x1800191c0  mov     rbx, [r11+18h]
0x1800191c4  mov     rsi, [r11+20h]
0x1800191c8  mov     rsp, r11
0x1800191cb  pop     rdi
0x1800191cc  retn
```
