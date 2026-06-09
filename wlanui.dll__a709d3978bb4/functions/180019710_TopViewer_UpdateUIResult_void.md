# TopViewer::UpdateUIResult(void)

- ea: `0x180019710`
- end: `0x1800198ad`
- name: `?UpdateUIResult@TopViewer@@AEAAHXZ`
- size: `413`
- prototype: `__int64 __fastcall(TopViewer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180017f48`

## callees

- `0x180001e26`
- `0x180019710`
- `0x18001ad24`
- `0x18001bf0a`
- `0x18001bf40`
- `0x18001d010`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001979b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001979b`
- `DUI70!StrToID` at `0x18001978f`
- `DUI70!StrToID` at `0x18001978f`
- `DUI70!?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z` at `0x1800197d7`
- `DUI70!?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z` at `0x1800197d7`

## pseudocode

```c
__int64 __fastcall TopViewer::UpdateUIResult(TopViewer *this)
{
  __int64 v1; // rax
  _QWORD *v3; // rax
  unsigned int v4; // edi
  unsigned __int64 v5; // rbx
  unsigned __int16 *DuiEditControlName; // rax
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rsi
  _WORD *v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rax
  size_t v12; // r8
  _QWORD *v13; // rax
  __int64 v14; // r8
  __int64 v16; // [rsp+20h] [rbp-858h] BYREF
  unsigned __int16 Src[1024]; // [rsp+30h] [rbp-848h] BYREF

  v1 = *((_QWORD *)this + 103);
  v16 = 0;
  if ( v1 )
  {
    v3 = *(_QWORD **)(v1 + 8);
    if ( v3 )
    {
      v4 = 0;
      v5 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v3[1] - *v3) >> 3);
      if ( (_DWORD)v5 )
      {
        do
        {
          DuiEditControlName = DuiDataHandler::GetDuiEditControlName(*((DuiDataHandler **)this + 103), v4);
          v7 = StrToID(DuiEditControlName);
          Descendent = DirectUI::Element::FindDescendent(this, v7);
          memset_0(Src, 0, sizeof(Src));
          if ( (*(unsigned __int8 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)Descendent + 16LL))(Descendent) )
          {
            DirectUI::Element::GetEncodedContentString(Descendent, Src, 0x400u);
          }
          else
          {
            v9 = (_WORD *)(*(__int64 (__fastcall **)(DirectUI::Element *, __int64 *))(*(_QWORD *)Descendent + 24LL))(
                            Descendent,
                            &v16);
            if ( v9 )
            {
              v10 = -1;
              do
                ++v10;
              while ( v9[v10] );
              v11 = 2 * v10;
              v12 = 2046;
              if ( v11 < 0x7FE )
                v12 = v11;
              memcpy_0(Src, v9, v12);
            }
          }
          v13 = *(_QWORD **)(*((_QWORD *)this + 103) + 8LL);
          if ( v13 && v4 < 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v13[1] - *v13) >> 3) )
          {
            v14 = -1;
            do
              ++v14;
            while ( Src[v14] );
            memcpy_0((void *)(*(_QWORD *)(*v13 + 24LL * v4 + 16) + 524LL), Src, 2 * v14 + 2);
          }
          ++v4;
        }
        while ( v4 < (unsigned int)v5 );
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180019710  push    rbx
0x180019712  push    rbp
0x180019713  push    rsi
0x180019714  push    rdi
0x180019715  push    r12
0x180019717  push    r14
0x180019719  sub     rsp, 848h
0x180019720  mov     rax, cs:__security_cookie
0x180019727  xor     rax, rsp
0x18001972a  mov     [rsp+878h+var_48], rax
0x180019732  mov     rax, [rcx+338h]
0x180019739  xor     r14d, r14d
0x18001973c  mov     [rsp+878h+var_858], r14
0x180019741  mov     rbp, rcx
0x180019744  test    rax, rax
0x180019747  jz      loc_180019888
0x18001974d  mov     rax, [rax+8]
0x180019751  test    rax, rax
0x180019754  jz      loc_180019888
0x18001975a  mov     rbx, [rax+8]
0x18001975e  mov     r12, 0AAAAAAAAAAAAAAABh
0x180019768  sub     rbx, [rax]
0x18001976b  mov     edi, r14d
0x18001976e  sar     rbx, 3
0x180019772  imul    rbx, r12
0x180019776  test    ebx, ebx
0x180019778  jz      loc_180019888
0x18001977e  mov     rcx, [rbp+338h]; this
0x180019785  mov     edx, edi; unsigned int
0x180019787  call    ?GetDuiEditControlName@DuiDataHandler@@QEAAPEAGK@Z; DuiDataHandler::GetDuiEditControlName(ulong)
0x18001978c  mov     rcx, rax
0x18001978f  call    cs:__imp_StrToID
0x180019795  movzx   edx, ax
0x180019798  mov     rcx, rbp
0x18001979b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800197a1  xor     edx, edx; Val
0x1800197a3  lea     rcx, [rsp+878h+Src]; void *
0x1800197a8  mov     r8d, 800h; Size
0x1800197ae  mov     rsi, rax
0x1800197b1  call    memset_0
0x1800197b6  mov     rax, [rsi]
0x1800197b9  mov     rcx, rsi
0x1800197bc  mov     rax, [rax+10h]
0x1800197c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197c5  mov     rcx, rsi
0x1800197c8  test    al, al
0x1800197ca  jz      short loc_1800197DF
0x1800197cc  mov     r8d, 400h
0x1800197d2  lea     rdx, [rsp+878h+Src]
0x1800197d7  call    cs:__imp_?GetEncodedContentString@Element@DirectUI@@QEAAJPEAG_K@Z; DirectUI::Element::GetEncodedContentString(ushort *,unsigned __int64)
0x1800197dd  jmp     short loc_180019820
0x1800197df  mov     rax, [rsi]
0x1800197e2  lea     rdx, [rsp+878h+var_858]
0x1800197e7  mov     rax, [rax+18h]
0x1800197eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197f0  mov     rdx, rax; Src
0x1800197f3  test    rax, rax
0x1800197f6  jz      short loc_180019820
0x1800197f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800197fc  inc     rax
0x1800197ff  cmp     [rdx+rax*2], r14w
0x180019804  jnz     short loc_1800197FC
0x180019806  add     rax, rax
0x180019809  lea     rcx, [rsp+878h+Src]; void *
0x18001980e  mov     r8d, 7FEh
0x180019814  cmp     rax, r8
0x180019817  cmovb   r8, rax; Size
0x18001981b  call    memcpy_0
0x180019820  mov     rax, [rbp+338h]
0x180019827  mov     rax, [rax+8]
0x18001982b  test    rax, rax
0x18001982e  jz      short loc_18001987E
0x180019830  mov     rdx, [rax]
0x180019833  mov     rax, [rax+8]
0x180019837  sub     rax, rdx
0x18001983a  mov     ecx, edi
0x18001983c  sar     rax, 3
0x180019840  imul    rax, r12
0x180019844  cmp     rcx, rax
0x180019847  jnb     short loc_18001987E
0x180019849  lea     rax, [rsp+878h+Src]
0x18001984e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019852  inc     r8
0x180019855  cmp     [rax+r8*2], r14w
0x18001985a  jnz     short loc_180019852
0x18001985c  lea     rcx, [rcx+rcx*2]
0x180019860  mov     rcx, [rdx+rcx*8+10h]
0x180019865  lea     r8, ds:2[r8*2]; Size
0x18001986d  add     rcx, 20Ch; void *
0x180019874  lea     rdx, [rsp+878h+Src]; Src
0x180019879  call    memcpy_0
0x18001987e  inc     edi
0x180019880  cmp     edi, ebx
0x180019882  jb      loc_18001977E
0x180019888  mov     eax, 1
0x18001988d  mov     rcx, [rsp+878h+var_48]
0x180019895  xor     rcx, rsp; StackCookie
0x180019898  call    __security_check_cookie
0x18001989d  add     rsp, 848h
0x1800198a4  pop     r14
0x1800198a6  pop     r12
0x1800198a8  pop     rdi
0x1800198a9  pop     rsi
0x1800198aa  pop     rbp
0x1800198ab  pop     rbx
0x1800198ac  retn
```
