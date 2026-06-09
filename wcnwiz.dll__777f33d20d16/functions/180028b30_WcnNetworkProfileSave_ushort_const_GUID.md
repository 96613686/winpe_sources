# WcnNetworkProfileSave(ushort const *,_GUID *)

- ea: `0x180028b30`
- end: `0x180028c62`
- name: `?WcnNetworkProfileSave@@YAJPEBGPEAU_GUID@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(LPCWSTR strProfileXml, struct _GUID *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000fab4`
- `0x1800100b0`
- `0x180020780`

## callees

- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x180028b30`
- `0x180028c68`
- `0x180028fc4`
- `0x18002de1c`

## string_xrefs

- `0x180028b9d`: `wszWlanXmlProfile`

## pseudocode

```c
__int64 __fastcall WcnNetworkProfileSave(LPCWSTR strProfileXml, struct _GUID *a2)
{
  _QWORD *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  int v8; // eax
  int FC; // eax
  int v10; // ebx
  _BYTE *v11; // r10
  unsigned int v12; // eax
  __int64 v13; // r10

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 27, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( strProfileXml )
  {
    v8 = WcnWlanProfileSaveToWlan(strProfileXml, a2);
    if ( v8 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids,
        (unsigned int)v8);
    FC = WcnWlanProfileSaveToLastFC(strProfileXml);
    v10 = FC;
    if ( FC < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)v10;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_18:
        if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v10 < 0 || v11[25] >= 6u) )
        {
          v12 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v13 + 16), 31, (unsigned int)WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v12, v10);
        }
        return (unsigned int)v10;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids,
        (unsigned int)FC);
    }
    v11 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
    WPP_SF_s(v4[2], 28, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, "wszWlanXmlProfile");
  return 2147500035LL;
}

```

## disassembly

```asm
0x180028b30  push    rbx
0x180028b32  push    rbp
0x180028b33  push    rsi
0x180028b34  push    rdi
0x180028b35  sub     rsp, 38h
0x180028b39  mov     rdi, rdx
0x180028b3c  mov     rbx, rcx
0x180028b3f  mov     r10, cs:WPP_GLOBAL_Control
0x180028b46  lea     rsi, WPP_GLOBAL_Control
0x180028b4d  lea     rbp, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180028b54  cmp     r10, rsi
0x180028b57  jz      short loc_180028B85
0x180028b59  cmp     byte ptr [r10+19h], 6
0x180028b5e  jb      short loc_180028B85
0x180028b60  mov     ecx, 1; int
0x180028b65  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180028b6a  mov     rcx, [r10+10h]
0x180028b6e  mov     edx, 1Bh
0x180028b73  mov     r9, rax
0x180028b76  mov     r8, rbp
0x180028b79  call    WPP_SF_s
0x180028b7e  mov     r10, cs:WPP_GLOBAL_Control
0x180028b85  test    rbx, rbx
0x180028b88  jnz     short loc_180028BB6
0x180028b8a  cmp     r10, rsi
0x180028b8d  jz      short loc_180028BAC
0x180028b8f  cmp     byte ptr [r10+19h], 2
0x180028b94  jb      short loc_180028BAC
0x180028b96  mov     rcx, [r10+10h]
0x180028b9a  lea     edx, [rbx+1Ch]
0x180028b9d  lea     r9, aWszwlanxmlprof; "wszWlanXmlProfile"
0x180028ba4  mov     r8, rbp
0x180028ba7  call    WPP_SF_s
0x180028bac  mov     eax, 80004003h
0x180028bb1  jmp     loc_180028C59
0x180028bb6  mov     rdx, rdi
0x180028bb9  mov     rcx, rbx; strProfileXml
0x180028bbc  call    WcnWlanProfileSaveToWlan
0x180028bc1  test    eax, eax
0x180028bc3  jns     short loc_180028BEB
0x180028bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bcc  cmp     rcx, rsi
0x180028bcf  jz      short loc_180028BEB
0x180028bd1  cmp     byte ptr [rcx+19h], 3
0x180028bd5  jb      short loc_180028BEB
0x180028bd7  mov     rcx, [rcx+10h]
0x180028bdb  mov     edx, 1Dh
0x180028be0  mov     r9d, eax
0x180028be3  mov     r8, rbp
0x180028be6  call    WPP_SF_d
0x180028beb  mov     rcx, rbx
0x180028bee  call    WcnWlanProfileSaveToLastFC
0x180028bf3  mov     ebx, eax
0x180028bf5  test    eax, eax
0x180028bf7  jns     short loc_180028C20
0x180028bf9  mov     r10, cs:WPP_GLOBAL_Control
0x180028c00  cmp     r10, rsi
0x180028c03  jz      short loc_180028C57
0x180028c05  cmp     byte ptr [r10+19h], 2
0x180028c0a  jb      short loc_180028C27
0x180028c0c  mov     rcx, [r10+10h]
0x180028c10  mov     edx, 1Eh
0x180028c15  mov     r9d, eax
0x180028c18  mov     r8, rbp
0x180028c1b  call    WPP_SF_d
0x180028c20  mov     r10, cs:WPP_GLOBAL_Control
0x180028c27  cmp     r10, rsi
0x180028c2a  jz      short loc_180028C57
0x180028c2c  test    ebx, ebx
0x180028c2e  js      short loc_180028C37
0x180028c30  cmp     byte ptr [r10+19h], 6
0x180028c35  jb      short loc_180028C57
0x180028c37  or      ecx, 0FFFFFFFFh; int
0x180028c3a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180028c3f  mov     rcx, [r10+10h]
0x180028c43  mov     edx, 1Fh
0x180028c48  mov     r9, rax
0x180028c4b  mov     [rsp+58h+var_38], ebx
0x180028c4f  mov     r8, rbp
0x180028c52  call    WPP_SF_sd
0x180028c57  mov     eax, ebx
0x180028c59  add     rsp, 38h
0x180028c5d  pop     rdi
0x180028c5e  pop     rsi
0x180028c5f  pop     rbp
0x180028c60  pop     rbx
0x180028c61  retn
```
