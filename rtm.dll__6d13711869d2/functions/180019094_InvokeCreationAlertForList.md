# InvokeCreationAlertForList

- ea: `0x180019094`
- end: `0x180019286`
- name: `InvokeCreationAlertForList`
- size: `498`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a360`
- `0x18001af20`

## callees

- `0x180019094`
- `0x18001b548`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## string_xrefs

- `0x1800191de`: `Invoked Creation Alert for protocol %x, %x`
- `0x180019115`: `Could not invoke CREATION_ALERTs since protocol(%ld, %ld) not found`
- `0x180019166`: `Protocol (%ld, %ld) does not have a CREATION_ALERT`

## pseudocode

```c
__int64 __fastcall InvokeCreationAlertForList(
        __int64 **a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 ProtocolEntry; // rax
  __int64 v10; // rdi
  __int64 *i; // rbx
  __int128 v13; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v14 = 0;
  v13 = 0;
  memset_0(v15, 0, sizeof(v15));
  ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, a2, a3);
  v10 = ProtocolEntry;
  if ( ProtocolEntry )
  {
    if ( *(_QWORD *)(ProtocolEntry + 48) )
    {
      for ( i = *a1; i != (__int64 *)a1; i = (__int64 *)*i )
      {
        *(_QWORD *)&v13 = __PAIR64__(a5, a4);
        DWORD2(v13) = 1;
        HIDWORD(v13) = *((_DWORD *)i + 10);
        if ( qword_18002B8A8 )
        {
          LOWORD(v14) = 0;
          FormatRRASErrorString(
            &v14,
            L"Invoked Creation Alert for protocol %x, %x",
            *(unsigned int *)(v10 + 16),
            *(unsigned int *)(v10 + 20));
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v14);
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, int, __int128 *))(v10 + 48))(
          *((unsigned int *)i + 4),
          *((unsigned int *)i + 5),
          *((unsigned int *)i + 6),
          *((unsigned int *)i + 7),
          *((_DWORD *)i + 8),
          *((_DWORD *)i + 9),
          1,
          &v13);
        *((_DWORD *)i + 10) = HIDWORD(v13);
      }
    }
    else if ( qword_18002B8A8 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"Protocol (%ld, %ld) does not have a CREATION_ALERT", a2, a3);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v14);
    }
    return 0;
  }
  else
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"Could not invoke CREATION_ALERTs since protocol(%ld, %ld) not found", a2, a3);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v14);
    }
    return 1168;
  }
}

```

## disassembly

```asm
0x180019094  push    rbp
0x180019096  push    rbx
0x180019097  push    rsi
0x180019098  push    rdi
0x180019099  push    r14
0x18001909b  push    r15
0x18001909d  lea     rbp, [rsp-778h]
0x1800190a5  sub     rsp, 878h
0x1800190ac  mov     rax, cs:__security_cookie
0x1800190b3  xor     rax, rsp
0x1800190b6  mov     [rbp+7A0h+var_40], rax
0x1800190bd  mov     r14d, r8d
0x1800190c0  mov     ebx, edx
0x1800190c2  mov     rsi, rcx
0x1800190c5  xorps   xmm0, xmm0
0x1800190c8  xor     eax, eax
0x1800190ca  lea     rcx, [rsp+8A0h+var_83C]; void *
0x1800190cf  xor     edx, edx; Val
0x1800190d1  mov     [rsp+8A0h+var_840], eax
0x1800190d5  mov     r8d, 7FCh; Size
0x1800190db  mov     r15d, r9d
0x1800190de  movups  [rsp+8A0h+var_850], xmm0
0x1800190e3  call    memset_0
0x1800190e8  mov     r8d, r14d
0x1800190eb  lea     rcx, qword_18002B9A8
0x1800190f2  mov     edx, ebx
0x1800190f4  call    GetProtocolEntry
0x1800190f9  mov     rdi, rax
0x1800190fc  test    rax, rax
0x1800190ff  jnz     short loc_18001914F
0x180019101  cmp     cs:qword_18002B8A8, rax
0x180019108  jz      short loc_180019145
0x18001910a  mov     r9d, r14d
0x18001910d  mov     word ptr [rsp+8A0h+var_840], ax
0x180019112  mov     r8d, ebx
0x180019115  lea     rdx, aCouldNotInvoke; "Could not invoke CREATION_ALERTs since "...
0x18001911c  lea     rcx, [rsp+8A0h+var_840]
0x180019121  call    FormatRRASErrorString
0x180019126  mov     rdx, cs:qword_18002B8A8
0x18001912d  lea     r8, [rsp+8A0h+var_840]
0x180019132  mov     rcx, cs:gMgmEtwContext
0x180019139  mov     rax, cs:gMgmTemplateFunc
0x180019140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019145  mov     eax, 490h
0x18001914a  jmp     loc_180019267
0x18001914f  cmp     qword ptr [rax+30h], 0
0x180019154  jnz     short loc_1800191A6
0x180019156  cmp     cs:qword_18002B8A8, 0
0x18001915e  jz      loc_180019265
0x180019164  xor     eax, eax
0x180019166  lea     rdx, aProtocolLdLdDo; "Protocol (%ld, %ld) does not have a CRE"...
0x18001916d  mov     r9d, r14d
0x180019170  mov     word ptr [rsp+8A0h+var_840], ax
0x180019175  mov     r8d, ebx
0x180019178  lea     rcx, [rsp+8A0h+var_840]
0x18001917d  call    FormatRRASErrorString
0x180019182  mov     rdx, cs:qword_18002B8A8
0x180019189  lea     r8, [rsp+8A0h+var_840]
0x18001918e  mov     rcx, cs:gMgmEtwContext
0x180019195  mov     rax, cs:gMgmTemplateFunc
0x18001919c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191a1  jmp     loc_180019265
0x1800191a6  mov     rbx, [rsi]
0x1800191a9  cmp     rbx, rsi
0x1800191ac  jz      loc_180019265
0x1800191b2  mov     r14d, [rbp+7A0h+arg_20]
0x1800191b9  cmp     cs:qword_18002B8A8, 0
0x1800191c1  mov     dword ptr [rsp+8A0h+var_850], r15d
0x1800191c6  mov     dword ptr [rsp+8A0h+var_850+4], r14d
0x1800191cb  mov     dword ptr [rsp+8A0h+var_850+8], 1
0x1800191d3  mov     eax, [rbx+28h]
0x1800191d6  mov     dword ptr [rsp+8A0h+var_850+0Ch], eax
0x1800191da  jz      short loc_18001921B
0x1800191dc  xor     eax, eax
0x1800191de  lea     rdx, aInvokedCreatio; "Invoked Creation Alert for protocol %x,"...
0x1800191e5  mov     word ptr [rsp+8A0h+var_840], ax
0x1800191ea  lea     rcx, [rsp+8A0h+var_840]
0x1800191ef  mov     r9d, [rdi+14h]
0x1800191f3  mov     r8d, [rdi+10h]
0x1800191f7  call    FormatRRASErrorString
0x1800191fc  mov     rdx, cs:qword_18002B8A8
0x180019203  lea     r8, [rsp+8A0h+var_840]
0x180019208  mov     rcx, cs:gMgmEtwContext
0x18001920f  mov     rax, cs:gMgmTemplateFunc
0x180019216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001921b  mov     ecx, [rbx+24h]
0x18001921e  lea     rax, [rsp+8A0h+var_850]
0x180019223  mov     r9d, [rbx+1Ch]
0x180019227  mov     r8d, [rbx+18h]
0x18001922b  mov     edx, [rbx+14h]
0x18001922e  mov     [rsp+8A0h+var_868], rax
0x180019233  mov     rax, [rdi+30h]
0x180019237  mov     [rsp+8A0h+var_870], 1
0x18001923f  mov     [rsp+8A0h+var_878], ecx
0x180019243  mov     ecx, [rbx+20h]
0x180019246  mov     [rsp+8A0h+var_880], ecx
0x18001924a  mov     ecx, [rbx+10h]
0x18001924d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019252  mov     eax, dword ptr [rsp+8A0h+var_850+0Ch]
0x180019256  mov     [rbx+28h], eax
0x180019259  mov     rbx, [rbx]
0x18001925c  cmp     rbx, rsi
0x18001925f  jnz     loc_1800191B9
0x180019265  xor     eax, eax
0x180019267  mov     rcx, [rbp+7A0h+var_40]
0x18001926e  xor     rcx, rsp; StackCookie
0x180019271  call    __security_check_cookie
0x180019276  add     rsp, 878h
0x18001927d  pop     r15
0x18001927f  pop     r14
0x180019281  pop     rdi
0x180019282  pop     rsi
0x180019283  pop     rbx
0x180019284  pop     rbp
0x180019285  retn
```
