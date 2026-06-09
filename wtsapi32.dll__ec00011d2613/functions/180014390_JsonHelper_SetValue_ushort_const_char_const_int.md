# JsonHelper::SetValue(ushort const *,char const *,int)

- ea: `0x180014390`
- end: `0x18001449b`
- name: `?SetValue@JsonHelper@@UEAAJPEBGPEBDH@Z`
- size: `267`
- prototype: `int(JsonHelper *__hidden this, const unsigned __int16 *, const char *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x180006734`
- `0x180014390`
- `0x1800144a4`
- `0x180014bb0`
- `0x180015488`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall JsonHelper::SetValue(JsonHelper *this, const unsigned __int16 *a2, const char *a3, int a4)
{
  int v6; // ebx
  int ActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // rcx
  void *Block; // [rsp+30h] [rbp-18h] BYREF

  Block = 0;
  v6 = JsonHelper::UTF8ToWideChar(this, a3, a4, (unsigned __int16 **)&Block);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(JsonHelper *, const unsigned __int16 *, void *))(*(_QWORD *)this + 120LL))(
           this,
           a2,
           Block);
    if ( v6 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v10, &WPP_GLOBAL_Control);
      v8 = 43;
      v9 = "this->SetValue";
      goto LABEL_11;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
    v8 = 42;
    v9 = "UTF8ToWideChar";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v9,
      v6);
  }
  if ( Block )
    operator delete(Block);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180014390  mov     r11, rsp
0x180014393  mov     [r11+8], rbx
0x180014397  mov     [r11+10h], rbp
0x18001439b  push    rsi
0x18001439c  sub     rsp, 40h
0x1800143a0  mov     eax, r9d
0x1800143a3  mov     qword ptr [r11-18h], 0
0x1800143ab  mov     r10, r8
0x1800143ae  lea     r9, [r11-18h]; unsigned __int16 **
0x1800143b2  mov     rbp, rdx
0x1800143b5  mov     r8d, eax; int
0x1800143b8  mov     rdx, r10; char *
0x1800143bb  mov     rsi, rcx
0x1800143be  call    ?UTF8ToWideChar@JsonHelper@@AEAAJPEBDHPEAPEAGPEAH@Z; JsonHelper::UTF8ToWideChar(char const *,int,ushort * *,int *)
0x1800143c3  mov     ebx, eax
0x1800143c5  test    eax, eax
0x1800143c7  jns     short loc_180014407
0x1800143c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143d0  lea     rdx, WPP_GLOBAL_Control
0x1800143d7  cmp     rcx, rdx
0x1800143da  jz      loc_180014477
0x1800143e0  test    byte ptr [rcx+1Ch], 8
0x1800143e4  jz      loc_180014477
0x1800143ea  cmp     byte ptr [rcx+19h], 2
0x1800143ee  jb      loc_180014477
0x1800143f4  call    RdpX_GetActivityIdPrefix
0x1800143f9  mov     edx, 2Ah ; '*'
0x1800143fe  lea     rcx, aUtf8towidechar; "UTF8ToWideChar"
0x180014405  jmp     short loc_180014454
0x180014407  mov     rax, [rsi]
0x18001440a  mov     rdx, rbp
0x18001440d  mov     r8, [rsp+48h+Block]
0x180014412  mov     rcx, rsi
0x180014415  mov     rax, [rax+78h]
0x180014419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001441e  mov     ebx, eax
0x180014420  test    eax, eax
0x180014422  jns     short loc_180014477
0x180014424  mov     rax, cs:WPP_GLOBAL_Control
0x18001442b  lea     rdx, WPP_GLOBAL_Control
0x180014432  cmp     rax, rdx
0x180014435  jz      short loc_180014477
0x180014437  test    byte ptr [rax+1Ch], 8
0x18001443b  jz      short loc_180014477
0x18001443d  cmp     byte ptr [rax+19h], 2
0x180014441  jb      short loc_180014477
0x180014443  call    RdpX_GetActivityIdPrefix
0x180014448  mov     edx, 2Bh ; '+'
0x18001444d  lea     rcx, aThisSetvalue; "this->SetValue"
0x180014454  mov     [rsp+48h+var_20], ebx
0x180014458  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18001445f  mov     [rsp+48h+var_28], rcx
0x180014464  mov     r9d, eax
0x180014467  mov     rcx, cs:WPP_GLOBAL_Control
0x18001446e  mov     rcx, [rcx+10h]
0x180014472  call    WPP_SF_DsD
0x180014477  cmp     [rsp+48h+Block], 0
0x18001447d  jz      short loc_180014489
0x18001447f  mov     rcx, [rsp+48h+Block]; Block
0x180014484  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014489  mov     rbp, [rsp+48h+arg_8]
0x18001448e  mov     eax, ebx
0x180014490  mov     rbx, [rsp+48h+arg_0]
0x180014495  add     rsp, 40h
0x180014499  pop     rsi
0x18001449a  retn
```
