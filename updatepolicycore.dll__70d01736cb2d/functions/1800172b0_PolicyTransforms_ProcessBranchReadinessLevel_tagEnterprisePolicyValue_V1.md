# PolicyTransforms::ProcessBranchReadinessLevel(tagEnterprisePolicyValue_V1 *)

- ea: `0x1800172b0`
- end: `0x180017451`
- name: `?ProcessBranchReadinessLevel@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800172b0`
- `0x18001efb4`
- `0x18002d630`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180017319`
- `OLEAUT32!__imp_SysAllocString` at `0x1800173f1`
- `OLEAUT32!__imp_SysAllocString` at `0x180017408`
- `OLEAUT32!__imp_SysAllocString` at `0x180017319`
- `OLEAUT32!__imp_SysAllocString` at `0x1800173f1`
- `OLEAUT32!__imp_SysAllocString` at `0x180017408`
- `OLEAUT32!__imp_VariantClear` at `0x180017353`
- `OLEAUT32!__imp_VariantClear` at `0x180017353`

## pseudocode

```c
__int64 __fastcall PolicyTransforms::ProcessBranchReadinessLevel(struct tagEnterprisePolicyValue_V1 *a1, int *a2)
{
  HRESULT v3; // ebx
  _WORD *v4; // r15
  BSTR v5; // rax
  int v6; // esi
  bool v7; // zf
  bool v8; // dl
  char v9; // al
  const OLECHAR *v10; // rcx
  BSTR v11; // rax
  int v13; // [rsp+20h] [rbp-38h] BYREF

  v3 = 0;
  v13 = 0;
  WUSystemInterfaceHelper::IsFlightingEnabled((WUSystemInterfaceHelper *)&v13, a2);
  if ( !a1 )
    return (unsigned int)-2147467261;
  v4 = (_WORD *)((char *)a1 + 16);
  if ( !(unsigned int)PolicyHelpers::GetSkuUpdateManagementGroupHelper() || *((_DWORD *)a1 + 1) != 1 )
  {
    *(_QWORD *)((char *)a1 + 4) = 3;
    *v4 = 8;
    v5 = SysAllocString(L"CB");
    *((_QWORD *)a1 + 3) = v5;
    return v5 == 0 ? 0x8007000E : 0;
  }
  if ( *v4 == 3 )
  {
    v6 = *((_DWORD *)a1 + 6);
    v3 = VariantClear((VARIANTARG *)((char *)a1 + 16));
    if ( v3 >= 0 )
    {
      v7 = v13 == 0;
      *v4 = 8;
      if ( v7 )
        goto LABEL_25;
      v8 = v6 == 64 || v6 == 128;
      if ( v6 == 8 )
        v8 = 1;
      v9 = v6 == 4 || v8;
      if ( v6 == 2 )
        v9 = 1;
      if ( !v9 )
      {
LABEL_25:
        *(_QWORD *)((char *)a1 + 4) = 3;
        v11 = SysAllocString(L"CB");
        *((_QWORD *)a1 + 3) = v11;
        v3 = v11 == 0 ? 0x8007000E : 0;
        goto LABEL_26;
      }
      switch ( v6 )
      {
        case 2:
          v10 = L"WIF";
          break;
        case 4:
          v10 = L"WIS";
          break;
        case 8:
          v10 = L"RP";
          break;
        case 64:
          v10 = L"RPQU";
          break;
        case 128:
          v10 = L"Canary";
          break;
        default:
LABEL_26:
          if ( *v4 == 8 && !*((_QWORD *)a1 + 3) )
            return (unsigned int)-2147024882;
          return (unsigned int)v3;
      }
      *((_QWORD *)a1 + 3) = SysAllocString(v10);
      goto LABEL_26;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800172b0  mov     [rsp+arg_8], rbx
0x1800172b5  mov     [rsp+arg_10], rbp
0x1800172ba  push    rsi
0x1800172bb  push    rdi
0x1800172bc  push    r12
0x1800172be  push    r14
0x1800172c0  push    r15
0x1800172c2  sub     rsp, 30h
0x1800172c6  mov     rax, cs:__security_cookie
0x1800172cd  xor     rax, rsp
0x1800172d0  mov     [rsp+58h+var_30], rax
0x1800172d5  mov     rdi, rcx
0x1800172d8  xor     ebx, ebx
0x1800172da  lea     rcx, [rsp+58h+var_38]; this
0x1800172df  mov     [rsp+58h+var_38], ebx
0x1800172e3  call    ?IsFlightingEnabled@WUSystemInterfaceHelper@@YAJPEAH@Z; WUSystemInterfaceHelper::IsFlightingEnabled(int *)
0x1800172e8  test    rdi, rdi
0x1800172eb  jnz     short loc_1800172F7
0x1800172ed  mov     ebx, 80004003h
0x1800172f2  jmp     loc_18001742B
0x1800172f7  lea     r15, [rdi+10h]
0x1800172fb  call    ?GetSkuUpdateManagementGroupHelper@PolicyHelpers@@SA?AW4tagUpdateManagementGroup@@XZ; PolicyHelpers::GetSkuUpdateManagementGroupHelper(void)
0x180017300  test    eax, eax
0x180017302  jnz     short loc_180017335
0x180017304  lea     rcx, aCb; "CB"
0x18001730b  mov     qword ptr [rdi+4], 3
0x180017313  mov     word ptr [r15], 8
0x180017319  call    cs:__imp_SysAllocString
0x18001731f  mov     [rdi+18h], rax
0x180017323  neg     rax
0x180017326  sbb     ebx, ebx
0x180017328  not     ebx
0x18001732a  and     ebx, 8007000Eh
0x180017330  jmp     loc_18001742B
0x180017335  mov     eax, 1
0x18001733a  cmp     [rdi+4], eax
0x18001733d  jnz     short loc_180017304
0x18001733f  lea     r14d, [rax+2]
0x180017343  cmp     [r15], r14w
0x180017347  jnz     loc_18001742B
0x18001734d  mov     esi, [rdi+18h]
0x180017350  mov     rcx, r15; pvarg
0x180017353  call    cs:__imp_VariantClear
0x180017359  mov     ebx, eax
0x18001735b  test    eax, eax
0x18001735d  js      loc_18001742B
0x180017363  cmp     [rsp+58h+var_38], 0
0x180017368  lea     ebp, [r14+5]
0x18001736c  mov     [r15], bp
0x180017370  mov     r12d, 8007000Eh
0x180017376  jz      loc_1800173FD
0x18001737c  lea     r8d, [r14+7Dh]
0x180017380  cmp     esi, r8d
0x180017383  setz    cl
0x180017386  cmp     esi, 40h ; '@'
0x180017389  setz    al
0x18001738c  or      cl, al
0x18001738e  cmp     esi, ebp
0x180017390  movzx   edx, cl
0x180017393  lea     ecx, [rbp-7]
0x180017396  cmovz   edx, ecx
0x180017399  cmp     esi, 4
0x18001739c  setz    al
0x18001739f  or      dl, al
0x1800173a1  cmp     esi, 2
0x1800173a4  movzx   eax, dl
0x1800173a7  cmovz   eax, ecx
0x1800173aa  test    al, al
0x1800173ac  jz      short loc_1800173FD
0x1800173ae  cmp     esi, 2
0x1800173b1  jnz     short loc_1800173BC
0x1800173b3  lea     rcx, aWif; "WIF"
0x1800173ba  jmp     short loc_1800173F1
0x1800173bc  cmp     esi, 4
0x1800173bf  jnz     short loc_1800173CA
0x1800173c1  lea     rcx, aWis; "WIS"
0x1800173c8  jmp     short loc_1800173F1
0x1800173ca  cmp     esi, ebp
0x1800173cc  jnz     short loc_1800173D7
0x1800173ce  lea     rcx, aRp; "RP"
0x1800173d5  jmp     short loc_1800173F1
0x1800173d7  cmp     esi, 40h ; '@'
0x1800173da  jnz     short loc_1800173E5
0x1800173dc  lea     rcx, aRpqu; "RPQU"
0x1800173e3  jmp     short loc_1800173F1
0x1800173e5  cmp     esi, r8d
0x1800173e8  jnz     short loc_18001741C
0x1800173ea  lea     rcx, aCanary; "Canary"
0x1800173f1  call    cs:__imp_SysAllocString
0x1800173f7  mov     [rdi+18h], rax
0x1800173fb  jmp     short loc_18001741C
0x1800173fd  lea     rcx, aCb; "CB"
0x180017404  mov     [rdi+4], r14
0x180017408  call    cs:__imp_SysAllocString
0x18001740e  mov     [rdi+18h], rax
0x180017412  neg     rax
0x180017415  sbb     ebx, ebx
0x180017417  not     ebx
0x180017419  and     ebx, r12d
0x18001741c  cmp     [r15], bp
0x180017420  jnz     short loc_18001742B
0x180017422  cmp     qword ptr [rdi+18h], 0
0x180017427  cmovz   ebx, r12d
0x18001742b  mov     eax, ebx
0x18001742d  mov     rcx, [rsp+58h+var_30]
0x180017432  xor     rcx, rsp; StackCookie
0x180017435  call    __security_check_cookie
0x18001743a  mov     rbx, [rsp+58h+arg_8]
0x18001743f  mov     rbp, [rsp+58h+arg_10]
0x180017444  add     rsp, 30h
0x180017448  pop     r15
0x18001744a  pop     r14
0x18001744c  pop     r12
0x18001744e  pop     rdi
0x18001744f  pop     rsi
0x180017450  retn
```
