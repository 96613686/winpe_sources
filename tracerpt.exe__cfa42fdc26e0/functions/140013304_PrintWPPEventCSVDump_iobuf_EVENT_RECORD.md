# PrintWPPEventCSVDump(_iobuf *,_EVENT_RECORD *)

- ea: `0x140013304`
- end: `0x14001355c`
- name: `?PrintWPPEventCSVDump@@YAXPEAU_iobuf@@PEAU_EVENT_RECORD@@@Z`
- size: `600`
- prototype: `void __fastcall(struct _iobuf *, PEVENT_RECORD pEvent)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d4a8`

## callees

- `0x140013304`
- `0x1400137b8`
- `0x1400161b0`

## string_xrefs

- `0x1400133a2`: `ComponentName`
- `0x1400133cf`: `SubComponentName`

## pseudocode

```c
void __fastcall PrintWPPEventCSVDump(struct _iobuf *a1, PEVENT_RECORD pEvent)
{
  if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 1) )
  {
    TracerptFPuts(", ", a1);
    if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 1) )
    {
      TracerptFPuts(", ", a1);
      if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 1) )
      {
        TracerptFPuts(", ", a1);
        if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 1) )
        {
          TracerptFPuts(", ", a1);
          if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 1) )
          {
            TracerptFPuts(", ", a1);
            if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 15) )
            {
              TracerptFPuts(", ", a1);
              if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 1) )
              {
                TracerptFPuts(", ", a1);
                if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 18) )
                {
                  TracerptFPuts(", ", a1);
                  if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 8) )
                  {
                    TracerptFPuts(", ", a1);
                    if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 1) )
                    {
                      TracerptFPuts(", ", a1);
                      if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 1) )
                      {
                        TracerptFPuts(", ", a1);
                        if ( !(unsigned int)PrintWPPProperty(a1, pEvent, 0, 17) )
                        {
                          TracerptFPuts(", ", a1);
                          PrintWPPProperty(a1, pEvent, 0, 15);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140013304  push    rbx
0x140013306  push    rbp
0x140013307  push    rsi
0x140013308  push    rdi
0x140013309  push    r14
0x14001330b  sub     rsp, 30h
0x14001330f  mov     ebp, 1
0x140013314  lea     r9, aGuidname; "GuidName"
0x14001331b  xor     r8d, r8d; unsigned __int8
0x14001331e  mov     [rsp+58h+var_38], bp; __int16
0x140013323  mov     rdi, rdx
0x140013326  mov     rbx, rcx
0x140013329  call    PrintWPPProperty
0x14001332e  test    eax, eax
0x140013330  jnz     loc_140013551
0x140013336  lea     rsi, asc_140045D74; ", "
0x14001333d  mov     rdx, rbx; struct _iobuf *
0x140013340  mov     rcx, rsi; Src
0x140013343  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140013348  lea     r9, aFunctionname; "FunctionName"
0x14001334f  mov     [rsp+58h+var_38], bp; __int16
0x140013354  xor     r8d, r8d; unsigned __int8
0x140013357  mov     rdx, rdi; pEvent
0x14001335a  mov     rcx, rbx; struct _iobuf *
0x14001335d  call    PrintWPPProperty
0x140013362  test    eax, eax
0x140013364  jnz     loc_140013551
0x14001336a  mov     rdx, rbx; struct _iobuf *
0x14001336d  mov     rcx, rsi; Src
0x140013370  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140013375  lea     r9, aFormattedstrin; "FormattedString"
0x14001337c  mov     [rsp+58h+var_38], bp; __int16
0x140013381  xor     r8d, r8d; unsigned __int8
0x140013384  mov     rdx, rdi; pEvent
0x140013387  mov     rcx, rbx; struct _iobuf *
0x14001338a  call    PrintWPPProperty
0x14001338f  test    eax, eax
0x140013391  jnz     loc_140013551
0x140013397  mov     rdx, rbx; struct _iobuf *
0x14001339a  mov     rcx, rsi; Src
0x14001339d  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400133a2  lea     r9, aComponentname; "ComponentName"
0x1400133a9  mov     [rsp+58h+var_38], bp; __int16
0x1400133ae  xor     r8d, r8d; unsigned __int8
0x1400133b1  mov     rdx, rdi; pEvent
0x1400133b4  mov     rcx, rbx; struct _iobuf *
0x1400133b7  call    PrintWPPProperty
0x1400133bc  test    eax, eax
0x1400133be  jnz     loc_140013551
0x1400133c4  mov     rdx, rbx; struct _iobuf *
0x1400133c7  mov     rcx, rsi; Src
0x1400133ca  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400133cf  lea     r9, aSubcomponentna; "SubComponentName"
0x1400133d6  mov     [rsp+58h+var_38], bp; __int16
0x1400133db  xor     r8d, r8d; unsigned __int8
0x1400133de  mov     rdx, rdi; pEvent
0x1400133e1  mov     rcx, rbx; struct _iobuf *
0x1400133e4  call    PrintWPPProperty
0x1400133e9  test    eax, eax
0x1400133eb  jnz     loc_140013551
0x1400133f1  mov     rdx, rbx; struct _iobuf *
0x1400133f4  mov     rcx, rsi; Src
0x1400133f7  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400133fc  lea     r14d, [rbp+0Eh]
0x140013400  xor     r8d, r8d; unsigned __int8
0x140013403  lea     r9, aTraceguid; "TraceGuid"
0x14001340a  mov     [rsp+58h+var_38], r14w; __int16
0x140013410  mov     rdx, rdi; pEvent
0x140013413  mov     rcx, rbx; struct _iobuf *
0x140013416  call    PrintWPPProperty
0x14001341b  test    eax, eax
0x14001341d  jnz     loc_140013551
0x140013423  mov     rdx, rbx; struct _iobuf *
0x140013426  mov     rcx, rsi; Src
0x140013429  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001342e  lea     r9, aGuidtypename; "GuidTypeName"
0x140013435  mov     [rsp+58h+var_38], bp; __int16
0x14001343a  xor     r8d, r8d; unsigned __int8
0x14001343d  mov     rdx, rdi; pEvent
0x140013440  mov     rcx, rbx; struct _iobuf *
0x140013443  call    PrintWPPProperty
0x140013448  test    eax, eax
0x14001344a  jnz     loc_140013551
0x140013450  mov     rdx, rbx; struct _iobuf *
0x140013453  mov     rcx, rsi; Src
0x140013456  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001345b  lea     r9, aSystemtime; "SystemTime"
0x140013462  mov     [rsp+58h+var_38], 12h; __int16
0x140013469  xor     r8d, r8d; unsigned __int8
0x14001346c  mov     rdx, rdi; pEvent
0x14001346f  mov     rcx, rbx; struct _iobuf *
0x140013472  call    PrintWPPProperty
0x140013477  test    eax, eax
0x140013479  jnz     loc_140013551
0x14001347f  mov     rdx, rbx; struct _iobuf *
0x140013482  mov     rcx, rsi; Src
0x140013485  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001348a  lea     r9, aSequencenum; "SequenceNum"
0x140013491  mov     [rsp+58h+var_38], 8; __int16
0x140013498  xor     r8d, r8d; unsigned __int8
0x14001349b  mov     rdx, rdi; pEvent
0x14001349e  mov     rcx, rbx; struct _iobuf *
0x1400134a1  call    PrintWPPProperty
0x1400134a6  test    eax, eax
0x1400134a8  jnz     loc_140013551
0x1400134ae  mov     rdx, rbx; struct _iobuf *
0x1400134b1  mov     rcx, rsi; Src
0x1400134b4  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400134b9  lea     r9, aFlagsname; "FlagsName"
0x1400134c0  mov     [rsp+58h+var_38], bp; __int16
0x1400134c5  xor     r8d, r8d; unsigned __int8
0x1400134c8  mov     rdx, rdi; pEvent
0x1400134cb  mov     rcx, rbx; struct _iobuf *
0x1400134ce  call    PrintWPPProperty
0x1400134d3  test    eax, eax
0x1400134d5  jnz     short loc_140013551
0x1400134d7  mov     rdx, rbx; struct _iobuf *
0x1400134da  mov     rcx, rsi; Src
0x1400134dd  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x1400134e2  lea     r9, aLevelname; "LevelName"
0x1400134e9  mov     [rsp+58h+var_38], bp; __int16
0x1400134ee  xor     r8d, r8d; unsigned __int8
0x1400134f1  mov     rdx, rdi; pEvent
0x1400134f4  mov     rcx, rbx; struct _iobuf *
0x1400134f7  call    PrintWPPProperty
0x1400134fc  test    eax, eax
0x1400134fe  jnz     short loc_140013551
0x140013500  mov     rdx, rbx; struct _iobuf *
0x140013503  mov     rcx, rsi; Src
0x140013506  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x14001350b  lea     r9, aRawsystemtime; "RawSystemTime"
0x140013512  mov     [rsp+58h+var_38], 11h; __int16
0x140013519  xor     r8d, r8d; unsigned __int8
0x14001351c  mov     rdx, rdi; pEvent
0x14001351f  mov     rcx, rbx; struct _iobuf *
0x140013522  call    PrintWPPProperty
0x140013527  test    eax, eax
0x140013529  jnz     short loc_140013551
0x14001352b  mov     rdx, rbx; struct _iobuf *
0x14001352e  mov     rcx, rsi; Src
0x140013531  call    ?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z; TracerptFPuts(char const *,_iobuf *)
0x140013536  lea     r9, aProviderguid; "ProviderGuid"
0x14001353d  mov     [rsp+58h+var_38], r14w; __int16
0x140013543  xor     r8d, r8d; unsigned __int8
0x140013546  mov     rdx, rdi; pEvent
0x140013549  mov     rcx, rbx; struct _iobuf *
0x14001354c  call    PrintWPPProperty
0x140013551  add     rsp, 30h
0x140013555  pop     r14
0x140013557  pop     rdi
0x140013558  pop     rsi
0x140013559  pop     rbp
0x14001355a  pop     rbx
0x14001355b  retn
```
