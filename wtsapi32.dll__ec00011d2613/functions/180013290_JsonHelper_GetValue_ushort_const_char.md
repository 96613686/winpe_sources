# JsonHelper::GetValue(ushort const *,char * *)

- ea: `0x180013290`
- end: `0x1800133de`
- name: `?GetValue@JsonHelper@@UEAAJPEBGPEAPEAD@Z`
- size: `334`
- prototype: `int(JsonHelper *__hidden this, const unsigned __int16 *, char **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012230`
- `0x180013290`
- `0x180014698`
- `0x180014bb0`
- `0x180015488`
- `0x1800155c0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001334d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001334d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800132cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800133c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800132cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800133c1`

## string_xrefs

- `0x18001333a`: `m_spJsonObj->GetNamedString failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetValue(JsonHelper *this, const unsigned __int16 *a2, char **a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  int ActivityIdPrefix; // eax
  int v10; // edx
  const char *v11; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  JsonHelper *v13; // rcx
  __int64 v14; // rdx
  int *v16; // [rsp+20h] [rbp-68h]
  UINT32 length; // [rsp+30h] [rbp-58h] BYREF
  HSTRING string; // [rsp+38h] [rbp-50h] BYREF
  const unsigned __int16 *v19; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v20[32]; // [rsp+48h] [rbp-40h] BYREF

  v3 = *((_QWORD *)this + 7);
  string = 0;
  length = 0;
  v19 = a2;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v3 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, &v19);
  v8 = v5(v3, *(_QWORD *)(v6 + 24), &string);
  if ( v8 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v8 = JsonHelper::WideCharToUTF8(v13, StringRawBuffer, length, a3, v16);
    if ( v8 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v14);
      v10 = 38;
      v11 = "WideCharToUTF8  failed!";
      goto LABEL_11;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v7);
    v10 = 37;
    v11 = "m_spJsonObj->GetNamedString failed!";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v11,
      v8);
  }
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180013290  push    rbx
0x180013292  push    rsi
0x180013293  push    rdi
0x180013294  sub     rsp, 70h
0x180013298  mov     rax, cs:__security_cookie
0x18001329f  xor     rax, rsp
0x1800132a2  mov     [rsp+88h+var_20], rax
0x1800132a7  mov     rdi, [rcx+38h]
0x1800132ab  mov     rsi, r8
0x1800132ae  mov     [rsp+88h+string], 0
0x1800132b7  xor     ecx, ecx; string
0x1800132b9  mov     [rsp+88h+length], 0
0x1800132c1  mov     [rsp+88h+var_48], rdx
0x1800132c6  mov     rax, [rdi]
0x1800132c9  mov     rbx, [rax+50h]
0x1800132cd  call    cs:__imp_WindowsDeleteString
0x1800132d3  lea     rdx, [rsp+88h+var_48]
0x1800132d8  mov     [rsp+88h+string], 0
0x1800132e1  lea     rcx, [rsp+88h+var_40]
0x1800132e6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800132eb  lea     r8, [rsp+88h+string]
0x1800132f0  mov     rcx, rdi
0x1800132f3  mov     rdx, [rax+18h]
0x1800132f7  mov     rax, rbx
0x1800132fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132ff  mov     ebx, eax
0x180013301  test    eax, eax
0x180013303  jns     short loc_180013343
0x180013305  mov     rax, cs:WPP_GLOBAL_Control
0x18001330c  lea     rcx, WPP_GLOBAL_Control
0x180013313  cmp     rax, rcx
0x180013316  jz      loc_1800133BC
0x18001331c  test    byte ptr [rax+1Ch], 8
0x180013320  jz      loc_1800133BC
0x180013326  cmp     byte ptr [rax+19h], 2
0x18001332a  jb      loc_1800133BC
0x180013330  call    RdpX_GetActivityIdPrefix
0x180013335  mov     edx, 25h ; '%'
0x18001333a  lea     rcx, aMSpjsonobjGetn; "m_spJsonObj->GetNamedString failed!"
0x180013341  jmp     short loc_180013399
0x180013343  mov     rcx, [rsp+88h+string]; string
0x180013348  lea     rdx, [rsp+88h+length]; length
0x18001334d  call    cs:__imp_WindowsGetStringRawBuffer
0x180013353  mov     r8d, [rsp+88h+length]; int
0x180013358  mov     r9, rsi; char **
0x18001335b  mov     rdx, rax; unsigned __int16 *
0x18001335e  call    ?WideCharToUTF8@JsonHelper@@AEAAJPEBGHPEAPEADPEAH@Z; JsonHelper::WideCharToUTF8(ushort const *,int,char * *,int *)
0x180013363  mov     ebx, eax
0x180013365  test    eax, eax
0x180013367  jns     short loc_1800133BC
0x180013369  mov     rax, cs:WPP_GLOBAL_Control
0x180013370  lea     rcx, WPP_GLOBAL_Control
0x180013377  cmp     rax, rcx
0x18001337a  jz      short loc_1800133BC
0x18001337c  test    byte ptr [rax+1Ch], 8
0x180013380  jz      short loc_1800133BC
0x180013382  cmp     byte ptr [rax+19h], 2
0x180013386  jb      short loc_1800133BC
0x180013388  call    RdpX_GetActivityIdPrefix
0x18001338d  mov     edx, 26h ; '&'
0x180013392  lea     rcx, aWidechartoutf8_0; "WideCharToUTF8  failed!"
0x180013399  mov     [rsp+88h+var_60], ebx
0x18001339d  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800133a4  mov     [rsp+88h+var_68], rcx
0x1800133a9  mov     r9d, eax
0x1800133ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133b3  mov     rcx, [rcx+10h]
0x1800133b7  call    WPP_SF_DsD
0x1800133bc  mov     rcx, [rsp+88h+string]; string
0x1800133c1  call    cs:__imp_WindowsDeleteString
0x1800133c7  mov     eax, ebx
0x1800133c9  mov     rcx, [rsp+88h+var_20]
0x1800133ce  xor     rcx, rsp; StackCookie
0x1800133d1  call    __security_check_cookie
0x1800133d6  add     rsp, 70h
0x1800133da  pop     rdi
0x1800133db  pop     rsi
0x1800133dc  pop     rbx
0x1800133dd  retn
```
